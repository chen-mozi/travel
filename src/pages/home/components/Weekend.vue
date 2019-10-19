<template>
  <div>
    <div class="weekend-trip">
      <h2>周末去哪儿</h2>
    </div>
    <div v-for="item of weekend" :key="item.id">
      <img class="weekend-img" :src="item.imgUrl" alt="">
      <div class="weekend-info">
        <p class="weekend-title">{{item.title}}</p>
        <p class="weekend-desc">{{item.desc}}</p>
      </div>
    </div>
  </div>
</template>

<script>
export default{
  name: 'HomeWeekend',
  props: {
    weekend: Array
  }
}
</script>

<style lang="stylus" scoped>
  @import '~styles/mixins.styl'
    .weekend-trip
      padding-left: 0.2rem
      font-size: 0.3rem
      background: #f5f5f5
      line-height: 0.8rem
    .weekend-img
     width: 100%
     border-top: 0.1rem solid #f5f5f5
    .weekend-info
      padding: 0.2rem
      min-width: 0
      .weekend-title
        color: #212121
        font-size: 0.3rem
        margin-bottom: 0.2rem
        ellipsis()
      .weekend-desc
        color: #212121
        font-size: 0.24rem
        ellipsis()
</style>
