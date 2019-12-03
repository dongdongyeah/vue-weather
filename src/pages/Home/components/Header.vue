<template>
  <div class='header'>
    <div class='city'>
      <router-link to='/city'>
        <span class='iconfont city-list'>&#xec70;</span>
      </router-link>
      <span class='city-name'>{{this.$store.state.city}}</span>
      <span v-if='isDay()' class='iconfont day-night'>&#xe672;</span>
      <span v-else class='iconfont day-night'>&#xe666;</span>
    </div>
    <div class='date'>{{headerToday.date_y}}</div>
    <div class='week'>{{headerToday.week}}</div>
  </div>
</template>

<script>
export default {
  name: 'HomeHeader',
  props: {
    headerToday: Object
  },
  methods: {
    /* 判断是白天还是黑夜 */
    isDay () {
      let now = new Date().getHours()
      return now > 6 && now < 19
    }
  }
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
