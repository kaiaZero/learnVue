<template>
  <div>
    <div class="search">
      <input class="search-input"
             placeholder="输入城市名"
             type="text"
             v-model="keyword"
             >
    </div>
    <div class="search-content"
          ref="search"
          v-show="keyword">
      <ul>
        <li class="search-item border-bottom"
            v-for="item of list"
            :key="item.id"
            @click="handleCityClick(item.name)">
          {{item.name}}
        </li>
        <li class="search-item border-bottom"
            v-show="!list.length">
          无匹配城市
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
import Bscroll from 'better-scroll'
export default {
  name: 'CitySearch',
  props: {
    cities: Object
  },
  data () {
    return {
      keyword: '',
      list: [],
      timer: null
    }
  },
  methods: {
    handleCityClick (city) {
      this.$store.commit('changeCity',city)
      this.$router.push('/')
    }
  },
  mounted () {
    this.scroll = new Bscroll(this.$refs.search)
  },
  watch: {
    keyword () {
      if (this.timer) {
        clearTimeout(this.timer)
      }
      if (!this.keyword) {
        this.list = []
      }
      this.timer = setTimeout(() => {
        const result = []
        for (let i in this.cities) {
          this.cities[i].forEach((value) => {
            if (value.spell.indexOf(this.keyword) > -1 ||
            value.name.indexOf(this.keyword) > -1) {
              result.push(value)
            }
          })
        }
        this.list = result
      }, 100)
    }
  }
}
</script>

<style lang='stylus' scoped>
  @import '~styles/variables.styl'
  .search
    height: .72rem
    background-color: $bgColor
    padding: 0 0.1rem
    .search-input
      box-sizing: border-box
      width: 100%
      line-height: 0.62rem
      height: 0.62rem
      text-align: center
      border-radius: 0.06rem
      color: #666
      padding: 0 0.1rem
  .search-content
    z-index: 1
    overflow: hidden
    position: absolute
    top: 1.58rem
    right: 0
    left: 0
    bottom:0
    .search-item
      line-height: 0.62rem
      padding-left :0.2rem
      background: #fff
      color: #666
</style>
