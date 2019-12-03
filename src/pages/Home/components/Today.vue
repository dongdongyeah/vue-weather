<template>
  <div class='today border-topbottom'>
    <div class='date'>今天</div>
    <div class='temp'>{{today.temperature}}</div>
    <div class='weather'>{{today.weather}}<img v-if='this.today.weather_id' class='img' :src='url'/></div>
  </div>
</template>

<script>

export default {
  name: 'Today',
  data () {
    return {
      nightUrl: '../../../../static/weather-icon/night',
      dayUrl: '../../../../static/weather-icon/day'
    }
  },
  props: {
    today: Object,
    isDay: Function
  },
  computed: {
    url () {
      let url = this.isDay ? (this.dayUrl + '/' + this.today.weather_id.fa + '.png') : (this.nightUrl + '/' + this.today.weather_id.fa + '.png')
      return url
    }
  }
}
</script>

<style lang='stylus' scoped>
.today
  display: flex
  justify-content: center
  font-size: .4rem
  line-height: .8rem
  padding: .3rem 0 .3rem
  color: #fff
  background: rgb(137, 196, 244)
  text-align: center
  .date
    width: 1.3rem
  .temp
    width: 2.5rem
  .weather
    width: 3.5rem
    .img
      margin-left: .2rem
</style>
