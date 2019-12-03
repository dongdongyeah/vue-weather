<template>
  <div class='realTime'>
    <div class='temp'><span class='temp-value'>{{sk.temp}}</span>℃</div>
    <div class='info'>
      <div class='wind'>
        <div class='wind-direction'><label>当前风向：</label>{{sk.wind_direction}}</div>
        <div class='wind-strength'><label>当前风力：</label>{{sk.wind_strength}}</div>
      </div>
      <div class='humidity'><label>当前湿度：</label>{{sk.humidity}}</div>
      <div class='updata-time'><label>更新时间：</label>{{sk.time}}</div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'RealTime',
  props: {
    sk: Object
  }
}
</script>

<style lang='stylus' scoped>
.realTime
  display: flex
  flex-direction: column
  padding: .4rem
  color: rgb(103, 128, 159)
  .temp
    font-size: .8rem
    font-weight: bold
    .temp-value
      font-size: 2rem
  .info
    line-height: .35rem
</style>
