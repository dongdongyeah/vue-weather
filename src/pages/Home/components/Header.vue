<template>
  <div class='header'>
    <div class='city'>
      <span class='iconfont cityList'>&#xe634;</span>
      <span class='cityName'>city</span>
    </div>
    <div class='date'>2019/11/30</div>
    <div class='week'>星期六</div>
  </div>
</template>

<script>
export default {
  name: 'HomeHeader'
}
</script>

<style lang='stylus' scoped>
.header
  display: flex
  flex-direction: column
  padding: .4rem
  color: #fff
  background: rgb(137, 196, 244)
  .city
    height: 1rem
    .cityList
      font-size: .5rem
    .cityName
      font-size: 1rem
  .date
    text-align: right
    margin-bottom: .2rem
  .week
    text-align: right
</style>
