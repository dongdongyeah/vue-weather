<template>
  <div class='header'>
    <div class='city'>
      <router-link to='/city'>
        <span class='iconfont city-list'>&#xec70;</span>
      </router-link>
      <span class='city-name'>邯郸</span>
      <span class='iconfont day-night'>&#xe666;</span>
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
  padding: .2rem .4rem
  .city
    display: flex
    flex-direction: row
    height: 1rem
    line-height: 1rem
    .city-list
      width: .8rem
      font-size: .5rem
      margin-right: .2rem
      color: #fff
    .city-name
      flex: 1
      font-size: .8rem
    .day-night
      font-size: .5rem
      text-align: right
  .date
    text-align: right
    margin-bottom: .2rem
  .week
    text-align: right
</style>
