<template>
  <div class='realTime'>
    <div class='temp'><span class='temp-value'>2</span>℃</div>
    <div class='info'>
      <div class='wind'>
        <div class='wind-direction'><label>当前风向：</label>西风</div>
        <div class='wind-strength'><label>当前风力：</label>2级</div>
      </div>
      <div class='humidity'><label>当前湿度：</label>4%</div>
      <div class='updata-time'><label>更新时间：</label>14:25</div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'RealTime'
}
</script>

<style lang='stylus' scoped>
.realTime
  display: flex
  flex-direction: column
  padding: .4rem
  .temp
    font-size: .8rem
    font-weight: bold
    color: rgb(103, 128, 159)
    .temp-value
      font-size: 2rem
  .info
    color: rgb(228, 241, 254)
    line-height: .35rem
</style>
