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
      <ul>
        <li class="hot-item-li" v-for="item of hot" :key="item.id" >
          <img class="hot-item-img-top" :src="item.imgTop">
          <img class="hot-item-img" :src='item.imgUrl' />
          <div class="hot-item-info">
            <p class="hot-item-title">{{item.title}}</p>
            <p class="hot-item-price">
              <span style="color: #ff8300">￥</span>
              <span>
                <span class="hot-item-price-one">{{item.price}}</span>
                起
              </span>
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
  props: {
    hot: Array
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
         min-width: 0.5rem
         padding:0 .1rem
         margin-top:0.1rem
         .hot-item-price-one
          font-size: 0.2rem
          color: #ff8300
          margin:0 -0.06rem
          font-weight: 700
</style>
