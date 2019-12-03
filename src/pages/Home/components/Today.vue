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
  justify-content: center
  font-size: .4rem
  line-height: .4rem
  padding: .3rem 0 .3rem
  background: rgb(228, 241, 254)
  color: rgb(44, 62, 80)
  background: #fff
  text-align: center
  .date
    width: 1.3rem
  .temp
    width: 2.5rem
  .weather
    width: 3.5rem
    .iconfont
      margin-left: .1rem
      font-size: .4rem
</style>
