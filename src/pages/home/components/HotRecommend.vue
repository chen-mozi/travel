<template>
  <div class="HotRecommend">
    <div class="hot-title">
      <div class="hot-title-info">
        <img class="hot-title-img" src="../../../../static/img/itemFire.png">
        <span>本周热门榜单</span>
      </div>
      <a class="hot-title-more"  href="#">全部榜单&nbsp;></a>
    </div>
    <div class="hot-item">
      <ul >
        <li class="hot-item-li" v-for="item of recommendList" :key="item.id">
          <img class="hot-item-img-top" :src="item.imgTop">
          <img class="hot-item-img" :src='item.imgUrl' />
          <div class="hot-item-info">
            <p class="hot-item-title">{{item.title}}</p>
            <p class="hot-item-price">
              <span  class="hot-item-price-one">{{item.price}}</span>
              <span >起</span>
            </p>
          </div>
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
export default {
  name: 'HomeHotRecommend',
  data () {
    return {
      recommendList: [{
        id: '0001',
        imgTop: './static/img/recommenTop01.png',
        imgUrl: './static/img/recommen01.jpg',
        title: '南昆山温泉大观园',
        price: '￥105'
      }, {
        id: '0002',
        imgTop: './static/img/recommenTop02.png',
        imgUrl: './static/img/recommen02.jpg',
        title: '罗浮山那里花开主题公园',
        price: '￥45'
      }, {
        id: '0003',
        imgTop: './static/img/recommenTop03.png',
        imgUrl: './static/img/recommen03.jpg',
        title: '南昆山云顶温泉',
        price: '￥91'
      }, {
        id: '0004',
        imgUrl: './static/img/recommen04.jpg',
        title: '欧美城文化小镇',
        price: '￥15'
      }]
    }
  }
}
</script>

<style lang="stylus" scoped>
  @import '~styles/mixins.styl'
.HotRecommend
   border-top: 0.2rem solid #f5f5f5
   overflow: hidden
  .hot-title
    position: relative
    margin-bottom: -0.2rem;
    .hot-title-info
      position: relative
      left: 0
      top:0.1rem
      .hot-title-img
        margin-bottom: 0.2rem
        margin-right:-0.15rem
        transform: scale(0.5)
        // background: url(../../../../static/img/itemFire.png)
    .hot-title-more
      font-size: 0.22rem
      position: relative
      right: -5.8rem
      bottom:0.46rem
      color: #333333
  .hot-item
    overflow: hidden
    // display: flex
    width:8888rem
    height: 3rem
    float: left
    margin-top:0.1rem
    .hot-item-li
      float:left
      position: relative
      padding-left: 0.2rem
      .hot-item-img-top
        transform: scale(0.5)
        position: absolute
        top: -0.2rem
        right:0.75rem
      .hot-item-img
        float:left
        width: 2rem
        height: 2rem
        margin-bottom: 0.1rem
      .hot-item-info
        font-size: 0.22rem
        text-align: center
        min-width:0
        .hot-item-title
          width:2rem
          ellipsis()
          // float: left
        .hot-item-price
         // float:left
         margin-top:0.1rem
         .hot-item-price-one
          color: #ff8e17
          font-weight: 700
</style>
