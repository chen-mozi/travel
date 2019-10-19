<template>
  <div class="icons">
    <swiper :options="swiperOption" v-if="icons.length">
      <swiper-slide v-for="(page,index) of pages" :key="index">
        <div class="icon"
             v-for="item of page"
             :key="item.id"
        >
          <div class="icon-img">
             <img class="icon-img-components" :src='item.imgUrl'>
          </div>
         <p class="icon-desc">{{item.desc}}</p>
        </div>
      </swiper-slide>
      <div class="swiper-pagination" slot="pagination"></div>
    </swiper>
  </div>
</template>

<script>
export default{
  name: 'HomeIcons',
  props: {
    icons: Array
  },
  data () {
    return {
      swiperOption: {
        pagination: '.swiper-pagination',
        loop: true,
        autoplay: false
      }
    }
  },
  computed: {
    pages () {
      const pages = []
      this.icons.forEach((item, index) => {
        const page = Math.floor(index / 8)
        if (!pages[page]) {
          pages[page] = []
        }
        pages[page].push(item)
      })
      return pages
    }
  }
}
</script>

<style lang="stylus" scoped>
  @import '~styles/varibles.styl'
  @import '~styles/mixins.styl'
  .icons >>>.swiper-container
    height: 0
    padding-bottom: 50%
  .icons
    margin-top: 0.2rem
    .icon
      position: relative
      float: left
      width: 25%
      height:0
      padding-bottom: 22%
      .icon-img
        position: absolute
        left:0
        right: 0
        top:0
        bottom: 0.3rem
        box-sizing:border-box
        padding: 0.1rem
        .icon-img-components
          display:block
          height:100%
          margin:0 auto
      .icon-desc
          position: absolute
          left:0
          right: 0
          bottom: 0
          height: 0.44rem
          line-height: 0.44rem
          text-align: center
          color:$darkTextColor
          ellipsis()

</style>
