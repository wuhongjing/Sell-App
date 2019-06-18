<template>
  <section id="app">
    <Header :seller="seller"></Header>
    <div class="tab">
       <ul>
          <router-link to="/"  tag="li" class="tabItem">商品</router-link>
          <router-link to="/ratings"  tag="li" class="tabItem">评论</router-link>
          <router-link to="/seller"  tag="li" class="tabItem">商家</router-link>
       </ul>
       <div>
          <router-view></router-view>
       </div>
    </div>
  </section>
</template>

<script>
import Header from './components/Header/Header'

const ERR_OK = 0
export default {
  name: 'App',
  components: {
    Header
  },
  data () {
    return {
      seller: {}
    }
  },
  created () {
    this.$http.get('/api/seller').then((res) => {
      res = res.body
      if (res.errno === ERR_OK) {
        this.seller = res.data
        console.log(this.seller)
      }
    })
  }
}
</script>
<style lang="stylus" scope>
@import "./common/stylus/mixin.styl"

.tab
  > ul
    display: flex
    width: 100%
    height: 40px
    line-height: 40px
    border-1px(rgba(7,17,27,0.1))
    .tabItem
      flex: 1
      text-align: center
      font-size: 14px
      color: rgb(77,85,93)
    .router-link-exact-active
      color: #ef3538
</style>
