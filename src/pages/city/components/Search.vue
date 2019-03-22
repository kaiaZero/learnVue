<template>
  <div class="search">
    <input class="search-input" placeholder="输入城市名" type="text">
  </div>
</template>

<script>
export default {
  name: 'CitySearch'
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

</style>
