<template>
  <div>
    <div class='header'>天气预报</div>
    <div
     class='today border-topbottom'
     v-for='(item, key) of futureList'
     :key=item[key]
    >
      <div class='date'>{{item.date}}</div>
      <div class='temp'>{{item.temperature}}</div>
      <div class='weather'>
        <img v-if='item' class='img' :src='dayUrl + "/" + item.weather_id.fa + ".png"'/>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Forecast',
  data () {
    return {
      dayUrl: '../../../../static/weather-icon/day'
    }
  },
  props: {
    futureList: Object
  },
  computed: {
    url () {
      let url = this.dayUrl + '/' + this.futureList.item.weather_id.fa + '.png'
      return url
    }
  }
}
</script>

<style lang='stylus' scoped>
.header
  height: .8rem
  line-height: .8rem
  font-size: .4rem
  text-align: center
  background: rgb(228, 241, 254)
  color: #666
.today
  display: flex
  justify-content: center
  align-items: center
  padding: .2rem 0 .2rem 0
  font-size: .35rem
  line-height: .35rem
  color: #fff
  background: rgb(137, 196, 244)
  text-align: center
  .date
    width: 2.2rem
  .temp
    width: 2rem
  .weather
    width: 2rem
</style>
