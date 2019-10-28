<template>
  <div class="container" @click="handleGallaryClick">
    <div class="wrapper">
      <swiper
        :options=" swiperOption">
        <swiper-slide
           v-for="(item, index) of imgs"
           :key="index"
        >
          <img class="gallary-img" :src="item" />
        </swiper-slide>
        <div class="swiper-pagination" slot="pagination"></div>
      </swiper>
    </div>
  </div>
</template>

<script>
export default {
  name: 'CommonGallary',
  props: {
    imgs: {
      tyep: Array,
      default () {
        return []
      }
    }
  },
  data () {
    return {
      swiperOption: {
        pagination: '.swiper-pagination',
        paginationType: 'fraction',
        observeParents: true,
        observer: true
      }
    }
  },
  methods: {
    handleGallaryClick () {
      this.$emit('close')
    }
  }
}
</script>
<style lang="stylus" scoped>
  .container >>>.swiper-container
    overflow: inherit
  .container
    display: flex
    flex-direction: column
    justify-content: center
    z-index: 9999
    position: fixed
    left: 0
    right: 0
    top: 0
    bottom:0
    background: #000
    .wrapper
      // position: relative
      .gallary-img
        width: 100%
        position: absolute
        top: 50%
        left: 50%
        transform: translate(-50%,-50%)
      .swiper-pagination
         color:#FFFFFF
         bottom: -5rem
         font-size: .24rem
</style>
