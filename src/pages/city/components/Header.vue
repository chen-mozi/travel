<template>
  <div class="header">
    <router-link to="/">
      <div class="iconfont header-icon">&#xe624;</div>
    </router-link>
    城市选择
  </div>
</template>
<script>
export default {
  name: 'CityHeader'
}
</script>

<style lang="stylus" scoped>
 @import '~styles/varibles.styl'
  .header
    overflow: hidden
    header: $headerHeight
    line-height: $headerHeight
    font-size: 0.32rem
    text-align: center
    color: #FFFFFF
    background: $bgColor
    .header-icon
      position: absolute
      top :0
      left :0.3rem
      font-size: 0.4rem
      color: #FFFFFF

</style>
