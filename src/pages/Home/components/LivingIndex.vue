<template>
  <div>
    <div class='header'>生活指数</div>
    <div class='living-index'>
      <div class='index border'>
        <div class='title'>穿衣指数</div>
        <div class='iconfont'>&#xe67a;</div>
        <div class='content'>较冷</div>
      </div>
      <div class='index border'>
        <div class='title'>穿衣建议</div>
        <div class='iconfont'>&#xe608;</div>
        <div class='content'>秋冬装</div>
      </div>
      <div class='index border'>
        <div class='title'>紫外线强度</div>
        <div class='iconfont'>&#xe632;</div>
        <div class='content'>中等</div>
      </div>
      <div class='index border'>
        <div class='title'>洗车指数</div>
        <div class='iconfont'>&#xe69a;</div>
        <div class='content'>较适宜</div>
      </div>
      <div class='index border'>
        <div class='title'>旅游指数</div>
        <div class='iconfont'>&#xe600;</div>
        <div class='content'>适宜</div>
      </div>
      <div class='index border'>
        <div class='title'>运动指数</div>
        <div class='iconfont'>&#xe65f;</div>
        <div class='content'>较适宜</div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'LivingIndex'
}
</script>

<style lang='stylus' scoped>
.header
  height: .6rem
  line-height: .6rem
  font-size: .3rem
  text-align: center
  background: rgb(228, 241, 254)
  color: #666
.living-index
  display: flex
  flex-wrap: wrap
  position: absolute
  color: #666
  text-align: center
  padding: 0
  margin: 0
  .index
    width: 2.5rem
    height: 0
    padding-bottom: 2.5rem
    .title
      margin-top: .3rem
      color: #666
    .iconfont
      margin-top: .2rem
      font-size: .8rem
      color: rgb(137, 196, 244)
    .content
      margin-top: .2rem
      font-size: .35rem
</style>
