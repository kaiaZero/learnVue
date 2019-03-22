<template>
  <div class="header">
    <router-link to="/">
    <div>
      <div class='iconfont header-back'>&#xe624;</div>
    </div>
    </router-link>
    城市选择
  </div>
</template>

<script>
export default {
  name: 'CityHeader'
}
</script>

<style lang='stylus' scoped>
  @import '~styles/variables.styl'
  .header
    height: $headerHeight
    line-height: $headerHeight
    overflow: hidden
    text-align: center
    color: #fff
    background-color: $bgColor
    font-size: 0.33rem
    position:relative
    .header-back
      position: absolute
      left:0
      top: 0
      width: 0.64rem
      font-size: 0.4rem
      text-align:center
      color: #fff
</style>
