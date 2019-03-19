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
          <p>{{item.description}}</p>
        </div>
      </swiper-slide>
    </swiper>
  </div>
</template>

<script>
export default {
  name: 'HomeIcons',
  data () {
    return {
      swiperOption: {
        autoplay: false
      },
      iconList: [{
        id: '001',
        imgUrl: 'https://imgs.qunarzz.com/piao/fusion/1803/95/f3dd6c383aeb3b02.png',
        description: '热门景点热门景点'
      }, {
        id: '002',
        imgUrl: 'https://imgs.qunarzz.com/piao/fusion/1803/95/f3dd6c383aeb3b02.png',
        description: '热门景点'
      }, {
        id: '003',
        imgUrl: 'https://imgs.qunarzz.com/piao/fusion/1803/95/f3dd6c383aeb3b02.png',
        description: '热门景点'
      }, {
        id: '004',
        imgUrl: 'https://imgs.qunarzz.com/piao/fusion/1803/95/f3dd6c383aeb3b02.png',
        description: '热门景点'
      }, {
        id: '005',
        imgUrl: 'https://imgs.qunarzz.com/piao/fusion/1803/95/f3dd6c383aeb3b02.png',
        description: '热门景点'
      }, {
        id: '006',
        imgUrl: 'https://imgs.qunarzz.com/piao/fusion/1803/95/f3dd6c383aeb3b02.png',
        description: '热门景点'
      }, {
        id: '007',
        imgUrl: 'https://imgs.qunarzz.com/piao/fusion/1803/95/f3dd6c383aeb3b02.png',
        description: '热门景点'
      }, {
        id: '008',
        imgUrl: 'https://imgs.qunarzz.com/piao/fusion/1803/95/f3dd6c383aeb3b02.png',
        description: '热门景点'
      }, {
        id: '009',
        imgUrl: 'https://imgs.qunarzz.com/piao/fusion/1803/95/f3dd6c383aeb3b02.png',
        description: '热门景点'
      }, {
        id: '010',
        imgUrl: 'https://imgs.qunarzz.com/piao/fusion/1803/95/f3dd6c383aeb3b02.png',
        description: '热门景点'
      }]
    }
  },
  computed: {
    pages () {
      const pages = []
      this.iconList.forEach((item, index) => {
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
