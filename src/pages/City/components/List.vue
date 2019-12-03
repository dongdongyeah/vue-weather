<template>
  <div class='list'>
    <div class='title'>当前城市</div>
    <div class='current-city'>
      <div class='cityname border'>{{this.$store.state.city}}</div>
    </div>
    <div class='title'>热门城市</div>
    <div class='hot-city'>
      <div
       class='cityname border'
       v-for='item of list'
       :key='item.id'
       @click='handleclick(item.district)'
      >
        {{item.district}}
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'CityList',
  props: {
    list: Array,
    currentcity: String
  },
  methods: {
    handleclick (city) {
      this.$store.dispatch('changeCity', city)
      this.$router.push('/')
    }
  }
}
</script>

<style lang='stylus' scoped>
.border
  &:before
    border-color: rgb(68, 108, 179)
    border-radius: 15px
.list
  color: rgb(68, 108, 179)
  .title
    line-height: .6rem
    padding: .1rem .3rem
    font-size: .3rem
    background: rgb(228, 241, 254)
    color: rgb(103, 128, 159)
  .current-city
  .hot-city
    display: flex
    flex-wrap: wrap
    justify-content: space-between
    width: 90%
    margin: .3rem auto
    .cityname
      width: 20%
      height: .4rem
      text-align: center
      line-height: .4rem
      padding: .1rem
      margin: .2rem .3rem
</style>
