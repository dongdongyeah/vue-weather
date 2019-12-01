<template>
  <div class='header'>
    <router-link to='/'>
      <div class='iconfont back'>&#xe6a8;</div>
    </router-link>
    <input class='input' type='text' placeholder='请输入要查询的城市名' value=''/>
    <router-link to='/'>
      <div class='iconfont search'>&#xe618;</div>
    </router-link>
  </div>
</template>

<script>
export default {
  name: 'CityHeader'
}
</script>

<style lang='stylus' scoped>
.header
  display: flex
  height: 1rem
  line-height: 1rem
  background: rgb(137, 196, 244)
  .iconfont
    width: 1rem
    font-size: .5rem
    text-align: center
    color: #fff
  .input
    height: .6rem
    margin: .2rem .1rem
    border-radius: 3px
    flex: 1
    padding: 0 .2rem
</style>
