<template>
  <div>
    <router-link
       class="header-abs"
       tag="div"
       to="/"
       v-if="showAbs"
    >
      <div class="iconfont abs-iconfont">&#xe624;</div>
    </router-link>
    <div
      class="header-fixed"
      v-if="!showAbs"
      :style="opacityStyle"
    >
      <router-link to="/">
        <div class="iconfont fiexd-iconfont">&#xe624;</div>
      </router-link>
      地派温泉
    </div>
  </div>
</template>

<script>
export default {
  name: 'DetailHeader',
  data () {
    return {
      showAbs: true,
      opacityStyle: {
        opacity: 0
      }
    }
  },
  methods: {
    handleScroll () {
      const top = document.documentElement.scrollTop
      if (top > 60) {
        let opacity = top / 140
        opacity = opacity > 1 ? 1 : opacity
        this.opacityStyle = {opacity}
        this.showAbs = false
      } else {
        this.showAbs = true
      }
    }
  },
  activated () {
    window.addEventListener('scroll', this.handleScroll)
  },
  deactivated () {
    window.removeEventListener('scroll', this.handleScroll)
  }
}
</script>

<style lang="stylus" scoped>
@import '~styles/varibles.styl'
  .header-abs
    position: absolute
    left: .1rem
    top: .1rem
    width: .7rem
    height: .7rem
    line-height: .7rem
    border-radius: .35rem
    background: rgba(0, 0, 0, 0.5)
    .abs-iconfont
      color: #FFFFFF
      font-weight: 700
      font-size: .35rem
      text-align: center
  .header-fixed
    position: fixed
    top: 0
    left: 0
    right:0
    overflow: hidden
    header: $headerHeight
    line-height: $headerHeight
    font-size: 0.32rem
    text-align: center
    background: $bgColor
    color: #FFFFFF
    .fiexd-iconfont
      position: absolute
      top :0
      left :0.2rem
      font-weight: 700
      font-size: .35rem
      color: #FFFFFF

</style>
