<template>
  <div class ="banner">
    <div class="wrapper">
      <swiper :options="swiperOption" v-if="showSwiper">
        <!-- slides -->
        <swiper-slide v-for="item of list" :key= "item.id">
          <!-- <img class="swiper-image" :src="getImgSrc(item)"> -->
          <img class="banner-img" :src="require(`@/assets/images/${item.imgUrl}`)">
        </swiper-slide>
        <div class="swiper-pagination"  slot="pagination"></div>
      </swiper>
    </div>
  </div>
</template>

<script>
export default {
  name: 'DetailBanner'
}
</script>

<style lang='stylus' scoped>
  .banner
    overflow: hidden
    height: 0
    padding-bottom: 55%
    background: green
</style>
