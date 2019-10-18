<template>
  <div>
    <div class="weekend-trip">
      <h2>周末去哪儿</h2>
    </div>
    <div v-for="item of weekendList" :key="item.id">
      <img class="weekend-img" :src="item.imgUrl" alt="">
      <div class="weekend-info">
        <p class="weekend-title">{{item.title}}</p>
        <p class="weekend-desc">{{item.desc}}</p>
      </div>
    </div>
  </div>
</template>

<script>
export default{
  name: 'HomeWeekend',
  data () {
    return {
      weekendList: [{
        id: '001',
        imgUrl: './static/img/weekend01.jpg',
        title: '深圳周边游',
        desc: '远离城市拥堵，去周边开启清新假期吧。'
      }, {
        id: '002',
        imgUrl: './static/img/weekend02.jpg',
        title: '惠州打卡圣地',
        desc: '毓秀山水，继续着四季轮回的交替'
      }, {
        id: '003',
        imgUrl: './static/img/weekend03.jpg',
        title: '清远周边逛',
        desc: '人人都有一双发现美的眼睛，身边的事物最熟悉不过，那你可曾发现了被人遗漏的美？'
      }]
    }
  }
}
</script>

<style lang="stylus" scoped>
  @import '~styles/mixins.styl'
    .weekend-trip
      padding-left: 0.2rem
      font-size: 0.3rem
      background: #f5f5f5
      line-height: 0.8rem
    .weekend-img
     width: 100%
     border-top: 0.1rem solid #f5f5f5
    .weekend-info
      padding: 0.2rem
      min-width: 0
      .weekend-title
        color: #212121
        font-size: 0.3rem
        margin-bottom: 0.2rem
        ellipsis()
      .weekend-desc
        color: #212121
        font-size: 0.24rem
        ellipsis()
</style>
