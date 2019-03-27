<template>
  <div>
    <div class= "recommend-title">热销推荐</div>
    <ul>
      <router-link
        tag="li"
        class="item border-bottom"
        v-for= "item of list"
        :key= "item.id"
        :to="'/detail/' + item.id"
      >
        <img class= "item-img" :src="item.imgUrl">
        <div class="item-info">
          <p class="item-title">{{item.title}}</p>
          <p class="item-desc">{{item.desc}}</p>
          <button>查看详情</button>
        </div>
      </router-link>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'HomeRecommend',
  props: {
    list: Array
  },
  data () {
    return {
      recommendList: [{
        id: '0001',
        imgUrl: 'https://imgs.qunarzz.com/sight/p0/1607/7c/7cda8b6782dabd80b4.img.jpg_200x200_2039e660.jpg',
        title: '上海迪士尼乐园',
        desc: '拥有七大主题园区：米奇大街、奇想花园、梦幻世界、探险岛、宝藏湾、明日世界和迪士尼•皮克斯玩具总动员主题园区。'
      }, {
        id: '0002',
        imgUrl: 'https://imgs.qunarzz.com/sight/p0/1607/7c/7cda8b6782dabd80b4.img.jpg_200x200_2039e660.jpg',
        title: '上海迪士尼乐园',
        desc: '拥有七大主题园区：米奇大街、奇想花园、梦幻世界、探险岛、宝藏湾、明日世界和迪士尼•皮克斯玩具总动员主题园区。'
      }, {
        id: '0003',
        imgUrl: 'https://imgs.qunarzz.com/sight/p0/1607/7c/7cda8b6782dabd80b4.img.jpg_200x200_2039e660.jpg',
        title: '上海迪士尼乐园',
        desc: '拥有七大主题园区：米奇大街、奇想花园、梦幻世界、探险岛、宝藏湾、明日世界和迪士尼•皮克斯玩具总动员主题园区。'
      }, {
        id: '0004',
        imgUrl: 'https://imgs.qunarzz.com/sight/p0/1607/7c/7cda8b6782dabd80b4.img.jpg_200x200_2039e660.jpg',
        title: '上海迪士尼乐园',
        desc: '拥有七大主题园区：米奇大街、奇想花园、梦幻世界、探险岛、宝藏湾、明日世界和迪士尼•皮克斯玩具总动员主题园区。'
      }]

    }
  }
}
</script>

<style lang='stylus' scoped>
  @import '~styles/mixins.styl'
  .recommend-title
    line-height: 0.8rem
    background-color: #eee
    text-indent: 0.2rem
    margin-top: 0.2rem
  .item
    display: flex
    overflow: hidden
    height: 1.9rem
    .item-img
      height: 1.7rem
      width: 1.7rem
      margin-top: 0.1rem
      margin-left: 0.1rem
    .item-info
      flex: 1
      padding: 0.1rem
      // min-width: 0
      overflow: hidden
      .item-title
        line-height: 0.54rem
        font-size: 0.32rem
        font-weight: bold
        ellipsis()
      .item-desc
        line-heiht: 0.4rem
        margin-top:0.1rem
        color: #aaa
        ellipsis()
      button
        background:#ff9300
        margin-top: 0.16rem
        line-height: 0.25rem
        padding: 0.2rem
        color: #fff
        font-weight: bold
        border-radius: 0.06rem
</style>
