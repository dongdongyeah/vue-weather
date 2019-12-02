<template>
  <div class='today border-topbottom'>
    <div class='date'>今天</div>
    <div class='temp'>{{today.temperature}}</div>
    <div class='weather'>{{today.weather}}<span class='iconfont'>&#xe642;</span></div>
  </div>
</template>

<script>

export default {
  name: 'Today',
  props: {
    today: Object
  }
}
</script>

<style lang='stylus' scoped>
.today
  display: flex
  padding: .2rem 1rem
  font-size: .4rem
  line-height: .4rem
  background: rgb(228, 241, 254)
  color: rgb(44, 62, 80)
  background: #fff
  .date
    width: 2rem
  .temp
    width: 2.5rem
  .weather
    .iconfont
      margin-left: .1rem
      font-size: .4rem
.forecast
  text-align: center
  padding: .2rem 0
  line-height: .4rem
  font-size: .3rem
</style>
