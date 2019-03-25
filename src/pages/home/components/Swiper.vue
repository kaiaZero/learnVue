<template>
  <div class="wrapper">
    <swiper :options="swiperOption" v-if="showSwiper">
      <!-- slides -->
      <swiper-slide v-for="item of list" :key= "item.id">
        <!-- <img class="swiper-image" :src="getImgSrc(item)"> -->
        <img class="swiper-image" :src="require(`@/assets/images/${item.imgUrl}`)">
      </swiper-slide>
      <div class="swiper-pagination"  slot="pagination"></div>
    </swiper>
  </div>
</template>

<script>
export default {
  name: 'HomeSwiper',
  props: {
    list: Array
  },
  computed: {
    showSwiper () {
      return this.list.length
    }
  },
  methods: {
    getImgSrc (item) {
      console.log(item.imgUrl)
      return require(`@/assets/images/${item.imgUrl}`)
    }
  },
  data () {
    return {
      swiperOption: {
        pagination: '.swiper-pagination',
        loop: true,
        autoplay: 3000
      }
    }
  }
}
</script>

<style lang='stylus' scoped>
.wrapper >>> .swiper-pagination-bullet-active
  background: #fff
.wrapper
  width:100%
  height:0
  overflow: hidden
  padding-bottom: 28.66%
  background-color: #eee
  .swiper-image
    width:100%
</style>
