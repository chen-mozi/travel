<template>
  <div class="wrapper">
    <swiper :options="swiperOption">
      <swiper-slide v-for="item of SwiperList" :key="item.id">
        <img class="swiper-img" :src="item.imgUrl" /></swiper-slide>
      <div class="swiper-pagination" slot="pagination"></div>
    </swiper>
  </div>
</template>

<script>
export default {
  name: 'HomeSwiper',
  data () {
    return {
      swiperOption: {
        pagination: '.swiper-pagination',
        loop: true
      },
      SwiperList: [{
        id: '0001',
        imgUrl: './static/img/swiper01.jpg'
      }, {
        id: '0002',
        imgUrl: './static/img/swiper02.jpg'
      }, {
        id: '0003',
        imgUrl: './static/img/swiper03.jpg'
      }, {
        id: '0004',
        imgUrl: './static/img/swiper04.jpg'
      }, {
        id: '0005',
        imgUrl: './static/img/swiper05.jpg'
      }]
    }
  }
}

</script>

<style lang="stylus" scoped>
  .wrapper >>>.swiper-pagination-bullet-active
    background: #fff
  .wrapper
    overflow: hidden
    width: 100%
    height: 0
    padding-bottom:  30.81%
    background: #eee
    .swiper-img
       width 100%
</style>
