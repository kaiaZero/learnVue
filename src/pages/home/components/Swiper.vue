<template>
  <div class="wrapper">
    <swiper :options="swiperOption" >
      <!-- slides -->
      <swiper-slide v-for="item of swiperList" :key= "item.id">
        <img class="swiper-image" :src="item.imgUrl">
      </swiper-slide>
      <div class="swiper-pagination"  slot="pagination"></div>
    </swiper>
  </div>
</template>

<script>
export default {
  name: 'HomeSwiper',
  data () {
    return {
      swiperOption: {
        pagination: '.swiper-pagination',
        loop: true,
        autoplay: 3000
      },
      swiperList: [{
        id: '001',
        imgUrl: require('@/assets/images/slide11.jpg')
      }, {
        id: '002',
        imgUrl: require('@/assets/images/slide12.jpg')
      }, {
        id: '003',
        imgUrl: require('@/assets/images/slide13.jpg')
      }, {
        id: '004',
        imgUrl: require('@/assets/images/slide14.jpg')
      }, {

        id: '005',
        imgUrl: require('@/assets/images/slide15.jpg')
      }
      ]
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
  padding-bottom: 26.66%
  background-color: #eee
  .swiper-image
    width:100%
</style>
