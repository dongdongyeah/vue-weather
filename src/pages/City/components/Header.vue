<template>
  <div>
    <div class='header'>
      <router-link to='/'>
        <div class='iconfont back'>&#xe6a8;</div>
      </router-link>
      <input v-model='keyword' class='input' type='text' placeholder='请输入要查询的城市名' value=''/>
      <router-link to='/'>
        <div class='iconfont search'>&#xe618;</div>
      </router-link>
    </div>
    <div v-show='showList' class='list'>
      <ul>
        <li
         class='border-top'
         v-for='item of keywordList'
         :key='item.id'
         @click='handleclick'
         >
         <span class='cityname'>{{item.district}}</span>, {{item.city}}市, {{item.province}}省
        </li>
        <li
         class='notdata'
         v-if='hasNotData'
        >
          对不起，没有找到匹配数据！
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
export default {
  name: 'CityHeader',
  data () {
    return {
      keyword: '',
      keywordList: []
    }
  },
  props: {
    list: Array
  },
  computed: {
    showList () {
      return this.keyword.length
    },
    hasNotData () {
      return !this.keywordList.length
    }
  },
  watch: {
    keyword () {
      this.keywordList = []
      for (let key in this.list) {
        if (this.list[key].district.indexOf(this.keyword) > -1) {
          this.keywordList.push(this.list[key])
        }
      }
    }
  },
  methods: {
    handleclick (e) {
      this.keyword = e.target.children[0].innerText
      this.$router.push('/')
      this.$emit('changecity', this.keyword)
    }
  }
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
.list
  z-index: 1
  position: absolute
  top: 1rem
  bottom: 0
  background: #fff
  width: 100%
  .border-top
    line-height: 1rem
    font-size: .3rem
    padding: 0 .4rem
  .notdata
    line-height: 1rem
    font-size: .3rem
    text-align: center
</style>
