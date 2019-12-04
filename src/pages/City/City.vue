<template>
  <div>
    <city-header
      :list='cityList'
      @changecity='changecity'
    >
    </city-header>
    <city-list
     :list='hotCityList'
     :currentcity='cityname'
    >
    </city-list>
  </div>
</template>

<script>
import CityHeader from '@/pages/City/components/Header'
import CityList from '@/pages/City/components/List'
import axios from 'axios'
export default {
  name: 'City',
  components: {
    CityHeader,
    CityList
  },
  data () {
    return {
      cityList: [],
      hotCityList: [],
      cityname: ''
    }
  },
  created () {
    this.getCityList()
  },
  methods: {
    getCityList () {
      axios.all([
        axios.get('/city.json', {baseURL: '/static/not-ignore'}),
        axios.get('/hotCityList.json', {baseURL: '/static/not-ignore'})
      ])
        .then(
          axios.spread(this.getSuccCity)
        )
    },
    getSuccCity (cityDate, hotCityData) {
      this.cityList = cityDate.data.result
      this.hotCityList = hotCityData.data.result
    },
    changecity (cityname) {
      this.cityname = cityname
    }
  }
}
</script>

<style lang='stylus' scoped>

</style>
