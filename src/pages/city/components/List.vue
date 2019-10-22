<template>
  <div class="list" ref="wrapper">
    <div>
      <div class="area">
        <div class="title border-topbottom">当前城市</div>
        <div class="button-list">
          <div class="button-wrapper">
            <div class="button">惠州</div>
          </div>
        </div>
      </div>
     <div class="area">
      <div class="title border-topbottom">热门城市</div>
       <div class="button-list">
         <div class="button-wrapper">
           <div class="button">惠州</div>
         </div>
         <div class="button-wrapper">
           <div class="button">惠州</div>
         </div>
         <div class="button-wrapper">
           <div class="button">惠州</div>
         </div>
      </div>
     </div>
      <div class="area">
        <div class="title border-topbottom">A</div>
        <ul class="item-list">
          <li class="item border-bottom">阿拉尔</li>
          <li class="item border-bottom">阿拉尔</li>
          <li class="item border-bottom">阿拉尔</li>
        </ul>
      </div>
    </div>
  </div>
</template>

<script>
import BScroll from 'better-scroll'
export default {
  name: 'CityList',
  mounted () {
    this.scroll = new BScroll(this.$refs.wrapper)
  }
}
</script>

<style lang="stylus" scoped>
   @import '~styles/varibles.styl'
    .border-topbottom
      &:before
        border-color: #CCCCCC
      &:after
        border-color: #CCCCCC
    .border-bottom
      &:before
        border-color: #CCCCCC
    .list
      overflow: hidden
      position: absolute
      top:1.67rem
      left: 0
      right: 0
      bottom: 0
      .title
        line-height: 0.54rem
        padding-left: 0.2rem
        font-size: 0.26rem
        background: #EEEEEE
        color: #666666
      .button-list
        padding: 0.1rem 0.6rem 0.1rem 0.1rem
        overflow: hidden
        .button-wrapper
          float: left
          width: 33.33%
          .button
            margin: 0.1rem
            padding: 0.1rem 0
            text-align: center
            border: 0.01rem solid #CCCCCC
      .item-list
        .item
          line-height: 0.72rem
          padding-left: 0.2rem

</style>
