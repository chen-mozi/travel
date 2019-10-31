<template>
  <div class="recommend">
    <div class="recommend-title">
      <img class="recommend-icon"  src="../../../../static/img/love.png">
      <span>猜你喜欢</span>
    </div>
    <ul
      class="like-list"
      v-for="item of love"
      :key="item.id"
    >
        <router-link
            class="list-item"
            :to="'/detail/' + item.id"
        >
         <div class="list-box">
           <div class="item-img-wrapper">
             <div class="item-img-info">
               <p class="top-title">{{item.topTitle}}</p>
               <img :src="item.imgTop" alt="">
             </div>
             <img class="item-img" :src="item.imgUrl">
           </div>
           <div class="item-info">
             <p class="item-title">{{item.title}}</p>
             <div class="item-desc">
               <span class="item-desc-start iconfont">
                 &#xe64b;&#xe64b;&#xe64b;&#xe64b;&#xe64b;
                 </span>
               <p class="item-comment">
                 <span>{{item.comment}}</span>
                 <span>条评论</span>
               </p>
             </div>
             <div class="item-like">
               <span style="color: #ff8300">￥</span>
               <span class="item-price">
                  <span class="item-price-number">
                  {{item.price}}
                  </span>
                  起
               </span>
               <span class="item-addres">{{item.addres}}</span>
             </div>
           </div>
          </div>
        </router-link>
    </ul>
    <a class="love-list-more" href="#">查看所有产品</a>
  </div>
</template>

<script>
export default {
  name: 'HomeLoveList',
  props: {
    love: Array
  }
}
</script>

<style lang="stylus" scoped>
  @import '~styles/mixins.styl'
  .recommend
    border-top: 0.2rem solid #f5f5f5
    overflow: hidden
    .recommend-title
      line-height: 1rem
      .recommend-icon
        margin-bottom: 0.2rem
        margin-right:-0.15rem
        transform: scale(0.5)
    .like-list
      padding-left: 0.2rem
      position: relative
      .list-box
        height: 2.5rem
        .item-img-wrapper
          .item-img-info
            // position: relative
            .top-title
              position: absolute
              top: 0.1rem
              left: 0.25rem
              font-size: 0.2rem
              color: #fff
              z-index: 1111
            img
              position: absolute
              // bottom: .2rem;
              left: 0.2rem
              width: 1.02rem
              height: .38rem
          .item-img
            width: 2rem
            height: 2rem
        .item-info
           position: relative
           bottom: 1.8rem
           left: 2.4rem
           min-width: 0
           .item-title
             width: 5rem
             color: #212121
             font-size: .32rem
             line-height: .44rem
             ellipsis()
           .item-desc
             width:2000rem
             .item-desc-start
               position: absolute
               left: 0
               top: 0.62rem
               font-size: 0.22rem
               color: #ffb436
             .item-comment
                position: absolute
                left: 1.6rem
                top: 0.6rem
                font-size: .24rem
                color: #616161
           .item-like
              margin-top: 0.9rem
              font-size: .24rem
              color: #616161
              .item-price
                min-width: 0.5rem
                padding:0 .2rem
                position: absolute
                top: 1.23rem
                left: 0
                // font-size: 0.4rem
                // color: #ff8300
                .item-price-number
                  font-size: 0.4rem
                  color: #ff8300
                  margin-right: -0.1rem
              .item-addres
                min-width: 1rem
                margin-right: 0.2rem
                position: absolute
                top: 1.33rem
                right: 2.5rem
    .love-list-more
      display: block
      font-size: .28rem
      line-height: .4rem
      color: #00afc7
      text-align: center
      padding: .2rem 0
      border-top: 0.01rem solid #f5f5f5

</style>
