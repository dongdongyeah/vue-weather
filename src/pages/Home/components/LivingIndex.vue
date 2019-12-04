<template>
  <div>
    <div class='header'>生活指数</div>
    <div class='living-index'>
      <div class='index border'>
        <div class='title'>穿衣指数</div>
        <div class='iconfont'>&#xe67a;</div>
        <div class='content'>{{today.dressing_index}}</div>
      </div>
      <div class='index border'>
        <div class='title'>穿衣建议</div>
        <div class='iconfont'>&#xe608;</div>
        <div class='content'>{{today.dressing_advice}}</div>
      </div>
      <div class='index border'>
        <div class='title'>紫外线强度</div>
        <div class='iconfont'>&#xe632;</div>
        <div class='content'>{{today.uv_index}}</div>
      </div>
      <div class='index border'>
        <div class='title'>洗车指数</div>
        <div class='iconfont'>&#xe69a;</div>
        <div class='content'>{{today.wash_index}}</div>
      </div>
      <div class='index border'>
        <div class='title'>旅游指数</div>
        <div class='iconfont'>&#xe600;</div>
        <div class='content'>{{today.travel_index}}</div>
      </div>
      <div class='index border'>
        <div class='title'>运动指数</div>
        <div class='iconfont'>&#xe65f;</div>
        <div class='content'>{{today.exercise_index}}</div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'LivingIndex',
  data () {
    return {
      message: 'this.today.dressing_advice'
    }
  },
  props: {
    today: Object
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
.living-index
  width: 100%
  display: flex
  flex-wrap: wrap
  justify-content: space-around
  padding: 0
  position: absolute
  color: #666
  text-align: center
  .index
    width: 33%
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
      font-size: .3rem
      overflow: hidden
      white-space: nowrap
      text-overflow: ellipsis
      box-sizing: border-box
      padding: 0 .2rem
    .content :hover
      color: red
</style>
