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
            <i></i><span>{{seller.supports[0].description}}</span>
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
   .content
     display: inline-block
     font-size: 14px
     margin-left: 16px
     .title
       margin: 2px 0 8px 0
       .brand
         display: inline-block
         width: 30px
         height: 18px
         bg-image('brand')
         background-size: 30px 18px
         background: no-repeate
</style>
