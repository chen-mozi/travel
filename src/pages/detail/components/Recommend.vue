<template>
  <div class="recommend">
    <div class="recommend-title">
      <img class="iconfont" src="../../../../static/img/itemFire.png">
      <span class="top-title">去哪儿推荐</span>
    </div>
    <div
      class="title-info border-topbottom"
      v-for="item of recommend" :key="item.id"
    >
      <div class="left">
        <h6 class="ticket-title">{{item.title}}</h6>
        <span class="ticket-desctag">
          <img :src="item.desctagImg" alt="">
          {{item.desctag}}
        </span>
        <ul >
          <li class="ticket-labelcon">
            <span class=" labelcon-blue">
              <img class="labelcon-img"  :src="item.labelconImg">
              <em>自营</em>
            </span>
            <span  class=" labelcon-blue">条件退</span>
            <span  class=" labelcon-red">赠券￥{{item.labelcon}}</span>
          </li>
        </ul>
      </div>
      <div class="right">
        <p class="right-price">
           ￥
          <em>{{item.price}}</em>
        </p>
        <p class="right-reserve">预订</p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'DetailRecommend',
  props: {
    recommend: Array
  }
}
</script>

<style  lang="stylus" scoped>
  .recommend-title
    height: .88rem
    line-height: .88rem
    .iconfont
      display: inline-block
      margin-top: -.15rem
      margin-left: .1rem
      transform: scale(0.65)
    .top-title
      font-size: .32rem
      margin-left: -.1rem
  .title-info
    overflow: hidden
    padding: .25rem .2rem
    .left
      width:75%
      float: left
      .ticket-title
        font-size: .3rem
        line-height: .4rem
      .ticket-desctag
        height: .32rem
        color: #616161
        font-size: .24rem
        img
          display: inline-block
          transform: scale(0.5)
          margin-right: -.1rem
          margin-bottom: .1rem
      .ticket-labelcon
        margin-top: -.05rem
        font-size: .2rem
        span
          margin-right: 0.1rem
          padding:.04rem
        .labelcon-blue
          color: #00afc7
          border: 0.01rem solid #a5e4ec
          .labelcon-img
            transform: scale(0.5)
            margin:0 -0.14rem
        .labelcon-red
          color: #f55
          border: 0.01rem solid #ffb2b2
    .right
      float: right
      padding-top: .15rem
      text-align: center
      .right-price
        color: #ff9800
        em
          margin-left: -.1rem
          font-size: .4rem
          line-height: .4rem
      .right-reserve
        color: #FFFFFF
        padding: .15rem 0.55rem
        border-radius: .08rem
        background-image: linear-gradient(130deg,#ffab1e 37%,#ff8c12 100%)

</style>
