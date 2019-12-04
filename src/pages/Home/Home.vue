<template>
  <div class='home'>
    <home-header
     :headerToday='today'
     :isDay='isDay'
    ></home-header>
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
      future: {},
      key: '10c213578f42636af4a2757fb63b28a1',
      lastCity: ''
    }
  },
  mounted () {
    this.lastCity = this.$store.state.city
    this.getDate()
  },
  activated () {
    if (this.lastCity !== this.$store.state.city) {
      this.lastCity = this.$store.state.city
      this.getDate()
    }
  },
  methods: {
    getDate () {
      /* axios.get(this.httpApi + '/index.json', { */
      axios.get('/index', {
        baseURL: '/weather',
        params: {
          key: this.key,
          cityname: this.$store.state.city
        }
      })
        .then(this.getSuccData)
    },
    getSuccData (res) {
      console.log(res)
      if (res.data.resultcode === '200' && res.data.reason === 'successed!') {
        this.today = res.data.result.today
        this.sk = res.data.result.sk
        this.future = res.data.result.future
      }
    },
    /* 判断是白天还是黑夜 */
    isDay () {
      let now = new Date().getHours()
      return now > 6 && now < 19
    }
  }
}
</script>

<style lang='stylus' scoped>
.home
  background: rgb(228, 241, 254)
  color: #fff
</style>
