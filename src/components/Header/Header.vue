<template>
   <section class="header">
     <div class="wrapper">
       <p class="avater">
         <img class="" width="64" height="64" :src="seller.avatar" >
       </p>
       <div class="content">
          <p class="title">
            <span class="brand"></span>
            <span class="name">{{seller.name}}</span>
          </p>
          <p class="time">
            {{seller.description}} / {{seller.deliveryTime}}分钟送达
          </p>
          <p class="describe" v-if="seller.supports">
            <i class="icon" :class="classMap[seller.supports[0].type]"></i><span class="text">{{seller.supports[0].description}}</span>
          </p>
       </div>
     </div>
   </section>
</template>

<script>
export default {
  name: 'Header',
  props: {
    seller: Object
  },
  created () {
    this.classMap = ['decrease', 'discount', 'guarantee', 'invoice', 'special']
  }
}
</script>

<style lang="stylus" rel="stylesheet/stylus" scoped>
@import '../../common/stylus/mixin';
.header
   background: #000
   color:#fff
   .wrapper
     padding: 24px 16px 18px 24px
     font-size: 0
     .avater
       display: inline-block
       vertical-align: top
       img
         border-radius: 2px
   .content
     display: inline-block
     font-size: 14px
     margin-left: 16px
     .title
       margin: 2px 0 8px 0
       .brand
         display: inline-block
         vertical-align: top
         width: 30px
         height: 18px
         bg-image('brand')
         background-size: 30px 18px
         background: no-repeate
       .name
          margin-left: 6px
          font-size: 16px
          line-height: 18px
          font-weight: bold
      .time
        margin-bottom: 10px
        line-height: 12px
        font-size: 12px
      .describe
        .icon
          display: inline-block
          width: 14px
          height: 14px
          margin-right: 4px
          background-size: 14px 14px
          &.decrease
            bg-image('decrease_1')
          &.discount
            bg-image('discount_1')
          &.guarantee
            bg-image('guarantee_1')
          &.invoice
            bg-image('invoice_1')
          &.special
            bg-image('special_1')
        .text
          font-size: 10px
          margin-left: 4px
          vertical-align: top
</style>
