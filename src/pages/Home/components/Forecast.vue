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
      <div class='weather'>{{item.weather}}<span class='iconfont'>&#xe642;</span></div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Forecast',
  props: {
    futureList: Object
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
  padding: .2rem 0 .2rem
  font-size: .3rem
  line-height: .4rem
  background: rgb(228, 241, 254)
  color: rgb(44, 62, 80)
  background: #fff
  text-align: center
  .date
    width: 2.5rem
  .temp
    width: 2.5rem
  .weather
    width: 3.5rem
    .iconfont
      margin-left: .1rem
      font-size: .3rem
</style>
