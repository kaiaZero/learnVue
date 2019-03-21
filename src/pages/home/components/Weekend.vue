<template>
  <div>
    <div class= "weekend-title">周末去哪儿</div>
    <ul>
      <li class="item border-bottom" v-for= "item of list" :key= "item.id">
        <div class= "wrapper">
          <img class= "item-img" :src="item.imgUrl">
        </div>
        <div class="item-info">
          <p class="item-title">{{item.title}}</p>
          <p class="item-desc">{{item.desc}}</p>
        </div>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'HomeWeekend',
  props: {
    list: Array
  },
  data () {
    return {
      recommendList: [{
        id: '0001',
        imgUrl: 'https://imgs.qunarzz.com/sight/source/1603/6d/2f67ae0659f41f.jpg_r_640x214_bf6cbd0b.jpg',
        title: '北京赏花好地方',
        desc: '乱花渐欲迷人眼，京城赏花大搜索'
      }, {
        id: '0002',
        imgUrl: 'https://imgs.qunarzz.com/sight/source/1603/6d/2f67ae0659f41f.jpg_r_640x214_bf6cbd0b.jpg',
        title: '北京赏花好地方',
        desc: '乱花渐欲迷人眼，京城赏花大搜索'
      }, {
        id: '0003',
        imgUrl: 'https://imgs.qunarzz.com/sight/source/1603/6d/2f67ae0659f41f.jpg_r_640x214_bf6cbd0b.jpg',
        title: '北京赏花好地方',
        desc: '乱花渐欲迷人眼，京城赏花大搜索'
      }, {
        id: '0004',
        imgUrl: 'https://imgs.qunarzz.com/sight/source/1603/6d/2f67ae0659f41f.jpg_r_640x214_bf6cbd0b.jpg',
        title: '北京赏花好地方',
        desc: '乱花渐欲迷人眼，京城赏花大搜索'
      }, {
        id: '0005',
        imgUrl: 'https://imgs.qunarzz.com/sight/source/1603/6d/2f67ae0659f41f.jpg_r_640x214_bf6cbd0b.jpg',
        title: '北京赏花好地方',
        desc: '乱花渐欲迷人眼，京城赏花大搜索'
      }]

    }
  }
}
</script>

<style lang='stylus' scoped>
  @import '~styles/mixins.styl'
  .weekend-title
    line-height: 0.8rem
    background-color: #eee
    text-indent: 0.2rem
    margin-top: 0.2rem
  .wrapper
    margin-top: 0.2rem
    height: 0
    padding-bottom: 38%
    overflow: hidden
    img
      width: 100%
  .item-info
    padding: 0.1rem
    overflow: hidden
    .item-title
      line-height: 0.54rem
      font-size: 0.32rem
      ellipsis()
    .item-desc
      line-heiht: 0.4rem
      margin-top:0.1rem
      font-size: 0.28rem
      color: #aaa
      ellipsis()

</style>
