<template>
  <div class= 'icons'>
    <swiper :options="swiperOption" >
      <swiper-slide v-for= "(item, index) of pages"
                    :key = "index"
      >
        <div class= 'icon'
             v-for= "item of item"
             :key= "item.id"
        >
          <div class= 'icon-image'>
            <img :src= 'item.imgUrl'/>
          </div>
          <p>{{item.desc}}</p>
        </div>
      </swiper-slide>
    </swiper>
  </div>
</template>

<script>
export default {
  name: 'HomeIcons',
  props: {
    list: Array
  },
  data () {
    return {
      swiperOption: {
        autoplay: false
      }
    }
  },
  computed: {
    pages () {
      const pages = []
      this.list.forEach((item, index) => {
        const page = Math.floor(index / 8)
        if (!pages[page]) {
          pages[page] = []
        }
        pages[page].push(item)
      })
      return pages
    }
  }
}
</script>

<style lang='stylus' scoped>
  @import '~styles/variables.styl'
  @import '~styles/mixins.styl'
  .icons >>> .swiper-container
    width: 100%
    height: 0
    padding-bottom: 50%
    overflow: hidden
  .icon
    position: relative
    width: 25%
    height: 0
    padding-bottom: 25%
    float: left
    overflow: hidden
    .icon-image
      position: absolute
      top: 0
      left: 0
      right: 0
      bottom: .44rem
      box-sizing: border-box
      padding: .1rem
      img
        display: block
        margin: 0 auto
        height: 100%
    p
      position: absolute
      bottom: 0
      left: 0
      right: 0
      height:0.44rem
      line-height: .44rem
      color: $darkTextColor
      text-align: center
      ellipsis()
</style>
