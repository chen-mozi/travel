<template>
  <div>
    <div
       class="item "
       v-for="(item, index) of list"
       :key="index"
    >
      <h3 class="title ">
        <span class="item-title-icon"></span>
        <span>{{item.title}}</span>
      </h3>
     <div class="titcket ">
       <div class="titcket-desc border-topbottom">
         <span class="titcket-title "> {{item.adult}}</span>
         <div class="titcket-info">
           ￥
           <span class="info-price">{{item.adultPrice}}</span>
           <span class="info-up">起</span>
         </div>
       </div>
       <div class="titcket-desc" v-if="item.children">
         <span class="titcket-title "> {{item.children}}</span>
         <div class="titcket-info">
           ￥
           <span class="info-price">{{item.childrenPrice}}</span>
           <span class="info-up">起</span>
         </div>
       </div>
       <div class="more border-topbottom">查看剩余产品</div>
     </div>
   </div>
 </div>
</template>

<script>
export default {
  name: 'DetailList',
  props: {
    list: Array
  }
}
</script>

<style lang="stylus" scoped>
  .item
    border-top: 0.15rem solid #EEEEEE
    .title
      line-height: .5rem
      font-size: .32rem
      margin: 0.2rem .2rem
     .item-title-icon
       position: relative
       top: .06rem
       left: .1rem
       display: inline-block
       width: .36rem
       height: .36rem
       background: url(http://s.qunarzz.com/piao/image/touch/sight/detail.png) 0 -.45rem no-repeat
       margin-right: .1rem
       background-size: .4rem 3rem
    .titcket
      // text-align: center
      line-height: .4rem
      .titcket-desc
        padding: 0.3rem 0.2rem
        // overflow: hidden
        .ticket-title
          float: left
          color: #333
          font-size: .3rem
          ine-height: .48rem
        .titcket-info
          float:right
          color: #ff9800
          padding-right: .2rem
          .info-price
            font-size: .4rem
            margin:0 -.1rem
          .info-up
            color: #9e9e9e
            font-size: .24rem
      .more
        text-align: center
        color: #616161
        height: .8rem
        line-height: 0.8rem

</style>
