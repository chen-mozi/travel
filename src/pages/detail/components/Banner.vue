<template>
  <div>
    <div class="banner" @click="handleBannerClick">
      <img class="banner-img" src="//img1.qunarzz.com/sight/p0/1907/23/23ab91e73359fe87a3.water.jpg_600x330_89a383af.jpg">
      <div class="banner-info">
        <div class="banner-number">
          <span class="iconfont banner-iconfont">&#xe63b;</span>
          <span class="iconfont-number">15</span>
        </div>
        <div class="banner-title">地派温泉</div>
      </div>
    </div>
    <common-gallary
      :imgs="imgs"
      v-show="showGallary"
      @close="handleGallaryClick"
    >
    </common-gallary>
  </div>
</template>

<script>
import CommonGallary from 'common/gallary/Gallary'
export default {
  name: 'DetailBanner',
  data () {
    return {
      showGallary: false,
      imgs: ['http://img1.qunarzz.com/sight/p0/1907/23/23ab91e73359fe87a3.water.jpg_r_800x800_eedb09a7.jpg',
        'http://img1.qunarzz.com/sight/p0/201403/10/de728cd5997f80fca3b7142ea329f677.jpg_r_800x800_64be80e1.jpg']
    }
  },
  methods: {
    handleBannerClick () {
      this.showGallary = true
    },
    handleGallaryClick () {
      this.showGallary = false
    }
  },
  components: {
    CommonGallary
  }
}
</script>
<style lang="stylus" scoped>
  .banner
    position: relative
    overflow: hidden
    height: 0
    padding-bottom: 55%
    .banner-img
      width: 100%
    .banner-info
      position: absolute
      left:0
      right: 0
      bottom:0
      line-height: .6rem
      color: #FFFFFF
      background-image: linear-gradient(to bottom, rgba(0, 0, 0, 0) ,rgba(0, 0, 0, 0.8))
      .banner-number
        width: 1.2rem
        height: .4rem
        line-height: .4rem
        position: absolute
        left: .2rem
        bottom: .86rem
        text-align: center
        border-radius: .2rem
        background: rgba(0, 0, 0, .5)
        .banner-iconfont
          position: absolute
          top: .02rem
          font-size: .29rem
        .iconfont-number
          font-size: 0.25rem
          margin-left: 0.35rem
      .banner-title
        position: relative
        left: 0.2rem
        bottom: 0.35rem
        line-height: 0.4rem
        font-size: .36rem

</style>
