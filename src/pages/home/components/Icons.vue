<template>
  <div class="icons">
    <swiper>
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
    </swiper>
  </div>
</template>

<script>
export default{
  name: 'HomeIcons',
  data () {
    return {
      iconList: [{
        id: '0001',
        imgUrl: './static/img/iconImg01.png',
        desc: '景点门票'
      }, {
        id: '0002',
        imgUrl: './static/img/iconImg02.png',
        desc: '惠州必游'
      }, {
        id: '0003',
        imgUrl: './static/img/iconImg03.png',
        desc: '惠州国庆'
      }, {
        id: '0004',
        imgUrl: './static/img/iconImg04.png',
        desc: '海滨海岛'
      }, {
        id: '0005',
        imgUrl: './static/img/iconImg05.png',
        desc: '广州融创'
      }, {
        id: '0006',
        imgUrl: './static/img/iconImg06.png',
        desc: '地派温泉'
      }, {
        id: '0007',
        imgUrl: './static/img/iconImg07.png',
        desc: '漂流'
      }, {
        id: '0008',
        imgUrl: './static/img/iconImg08.png',
        desc: '海洋馆'
      }, {
        id: '0009',
        imgUrl: './static/img/iconImg09.png',
        desc: '水上玩乐'
      }, {
        id: '0010',
        imgUrl: './static/img/iconImg10.png',
        desc: '玩转长隆'
      }]
    }
  },
  computed: {
    pages () {
      const pages = []
      this.iconList.forEach((item, index) => {
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
    .icon
      position: relative
      float: left
      width: 25%
      height:0
      padding-bottom: 25%
      .icon-img
        position: absolute
        left:0
        right: 0
        top:0
        bottom: 0.44rem
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
