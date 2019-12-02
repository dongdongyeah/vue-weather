<template>
  <div class='home'>
    <home-header :headerToday='today'></home-header>
    <real-time :sk='sk'></real-time>
    <today :today='today'></today>
    <forecast :futureList='future'></forecast>
    <living-index :today='today'></living-index>
  </div>
</template>

<script>
import HomeHeader from '@/pages/Home/components/Header'
import RealTime from '@/pages/Home/components/RealTime'
import Today from '@/pages/Home/components/Today'
import Forecast from '@/pages/Home/components/Forecast'
import LivingIndex from '@/pages/Home/components/LivingIndex'
import axios from 'axios'
axios.defaults.baseURL = '/weather'
export default {
  name: 'Home',
  components: {
    HomeHeader,
    RealTime,
    Today,
    Forecast,
    LivingIndex
  },
  data () {
    return {
      httpApi: process.env.API_HOST,
      today: {},
      sk: {},
      future: {}
    }
  },
  created () {
    /* this.getDate() */
  },
  methods: {
    /* getDate () {
      axios.get(this.httpApi + '/index.json', {
        key: '10c213578f42636af4a2757fb63b28a1',
        cityname: '北京'
      })
        .then(this.getSuccData)
    }, */
    getSuccData (res) {
      if (res.data.resultcode === '200' && res.data.reason === 'successed!') {
        this.today = res.data.result.today
        this.sk = res.data.result.sk
        this.future = res.data.result.future
      }
    }
  }
}
</script>

<style lang='stylus' scoped>
.home
  background: rgb(137, 196, 244)
  color: #fff
</style>
