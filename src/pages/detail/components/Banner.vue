<template>
  <div>
    <div class="banner" @click="handleBannerClick">
      <img class="banner-img" :src="bannerImg" />
      <div class="banner-info">
        <div class="banner-number">
          <span class="iconfont banner-iconfont">&#xe63b;</span>
          <span class="iconfont-number">{{this.bannerImgs.length}}</span>
        </div>
        <div class="banner-title">{{this.sightName}}</div>
      </div>
    </div>
    <fade-animation>
      <common-gallary
        :imgs="bannerImgs"
        v-show="showGallary"
        @close="handleGallaryClick"
      >
      </common-gallary>
    </fade-animation>
  </div>
</template>

<script>
import CommonGallary from 'common/gallary/Gallary'
import FadeAnimation from 'common/fade/Fade'
export default {
  name: 'DetailBanner',
  props: {
    sightName: String,
    bannerImg: String,
    bannerImgs: Array
  },
  data () {
    return {
      showGallary: false
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
    CommonGallary,
    FadeAnimation
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
