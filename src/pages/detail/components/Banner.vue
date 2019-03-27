<template>
  <div>
    <div class ="banner" @click="handleBannerClick">
      <img class="banner-img"
           src="//img1.qunarzz.com/sight/p0/1409/19/adca619faaab0898245dc4ec482b5722.jpg_600x330_f922b488.jpg" />
      <div class="banner-info">
        <div class="banner-title">
          故宫(AAAAA景区)
        </div>
        <div class="banner-number">
          <span class='iconfont banner-icon'>&#xe67f;</span>39
        </div>
      </div>
    </div>
    <common-gallary
      :imgs="imgs"
      v-if="showGallary"
      @close="handleGallaryClose"
      >
    </common-gallary>
  </div>
</template>

<script>
import CommonGallary from 'common/gallary/Gallary'
export default {
  name: 'DetailBanner',
  components: {
    CommonGallary
  },
  data () {
    return {
      showGallary: false,
      imgs: ['http://img1.qunarzz.com/sight/p55/201211/04/fbcab3e5d6479ce893835fbb.jpg', 'http://img1.qunarzz.com/wugc/p123/201211/19/a2045d091f02b25493835fbb.png_r_800x800_c59f0eba.png']
    }
  },
  methods: {
    handleBannerClick () {
      this.showGallary = true
    },
    handleGallaryClose () {
      this.showGallary = false
    }
  }
}
</script>

<style lang='stylus' scoped>
  .banner
    position: relative
    overflow: hidden
    height: 0
    padding-bottom: 55%
    background: green
    .banner-img
      width: 100%
    .banner-info
      position: absolute
      left: 0
      right:0
      bottom: 0
      line-height: 0.6rem
      display: flex
      color: #fff
      background-image: linear-gradient(top,rgba(0,0,0,0),rgba(0,0,0,0.8))
      .banner-title
        flex: 1
        font-size: 0.32rem
        padding: 0 0.2rem
      .banner-number
        padding: 0 0.4rem
        height:0.32rem
        font-size: 0.24rem
        line-height: 0.4rem
        margin-top: 0.14rem
        border-radius: 0.2rem
        background: rgba(0,0,0,0.8)
        font-size: 0.24rem
        .banner-icon
          font-size: 0.24rem
</style>
