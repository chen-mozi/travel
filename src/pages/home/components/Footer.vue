<template>
  <div>
    <div class="footer-title">
      <div class="footer-title-desc">
        <span class="footer-price-icon iconfont">&#xe602;</span>
        <span class="price-desc">
          <strong class="price-desc-height">票面价</strong>
          是指通过景区指定窗口售卖的纸质门票上标注的价格
        </span>
      </div>
    </div>
    <div class="footer">
        <ul class="info-desc">
          <li class="icons">
              <a href="#">
                <span class="iconfont">&#xe70e;</span>
                <span class="icon-type">机票</span>
              </a>
          </li>
          <li class="icons">
              <a href="#">
                <span class="iconfont">&#xe61b;</span>
                <span class="icon-type">酒店</span>
              </a>
          </li>
          <li class="icons">
              <a href="#">
                <span class="iconfont">&#xe662;</span>
                <span class="icon-type">公寓</span>
              </a>
          </li>
          <li class="icons">
              <a href="#">
                <span class="iconfont">&#xe714;</span>
                <span class="icon-type type-more">更多</span>
              </a>
          </li>
        </ul>
        <ul class="user" >
          <li class="user-info">
            <a href="#">登录</a>
          <li class="user-info">
            <a href="#">我的订单</a>
          </li>
          <li class="user-info">
            <a href="#">最近浏览</a>
          </li>
          <li class="user-info">
            <a href="#">关于我们</a>
          </li>
        </ul>
        <ul class="mobile">
          <a href="#" class="mobile-one">触屏版</a>
          <a href="#" class="mobile-two">电脑版</a>
        </ul>
        <div class="copyright">
          <span>Qunar 京ICP备05021087</span>
          <a href="#">意见反馈</a>
        </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'HomeFooter'
}
</script>

<style lang="stylus" scoped>
  .footer-title
    background: #FFFFFF
    border-top: 0.15rem solid #EEEEEE
    .footer-title-desc
      padding: 0.15rem  0.1rem
      .footer-price-icon
        font-size: 0.25rem
      .price-desc
        font-size: 0.24rem
       .price-desc-height
          font-weight: 700
  .footer
    position: absolute
    width: 100%
    background: #EEEEEE
    .info-desc
      display: flex
      margin: 0.1rem 1rem
      position: relative
      .icons
        float: left
        padding: 0.1rem 0.2rem
        .iconfont
          font-size: 0.43rem
          color: #acacac
          padding-top 0.2rem
        .icon-type
          position: relative
          bottom: 0.06rem
          left: 0rem
          color: #acacac
          font-size: 0.2rem
          border-bottom: 0.01rem solid #ACACAC
        .type-more
          font-size: 0.3rem
          border: none
    .user
      position: relative
      display: flex
      .user-info
        float: left
        line-height: 0.8rem
        padding-left: 0.5rem
        font-size: 0.28rem
        // border-bottom: 0.03rem solid #cacaca
        a
          display: inline-block
          color: #25a4bb
    .mobile
      position: relative
      display: flex
      padding:0.2rem 2.5rem
      border-top: 0.02rem solid #cacaca
      .mobile-one
        display: inline-block
        color: #000000
      .mobile-two
        display: inline-block
        color: #25a4bb
        padding-left: 0.5rem
    .copyright
      color: #9e9e9e
      padding: 0 1.5rem
      margin-bottom: 0.2rem
      a
        display: inline-block
        color: #9e9e9e

</style>
