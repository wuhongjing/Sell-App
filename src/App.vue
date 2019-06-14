<template>
  <section id="app">
    <Header></Header>
    <div class="tab">
       <ul>
          <li class="tabItem">商品</li>
          <li class="tabItem">评论</li>
          <li class="tabItem">商家</li>
       </ul>
    </div>
  </section>
</template>

<script>
import Header from './components/Header/Header'
export default {
  name: 'App',
  components: {
    Header
  }
}
</script>

<style lang="stylus" scope>
.tab
  > ul
    display: flex
    width: 100%
    height: 40px
    line-height: 40px
    > li
      flex: 1
      text-align: center
</style>
