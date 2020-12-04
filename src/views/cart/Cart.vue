<template>
  <div class="cart">
    <!-- 导航 -->
    <nav-bar class="nav-bar">
      <div slot="center" >购物车({{cartLength}})</div>
    </nav-bar>

    <!-- 商品列表 -->
    <scroll class="content" ref="scroll"> 
      
      <cart-list />
    </scroll>
    

    <!-- 底部汇总 -->
    <cart-bottom-bar />
  </div>
</template>

<script>
import NavBar from 'components/common/navbar/NavBar.vue'
import CartList from './childComps/CartList.vue'
import Scroll from 'components/common/scroll/Scroll.vue'
import CartBottomBar from './childComps/CartBottomBar.vue'

import {mapGetters} from 'vuex'

  export default {
    name: "Cart",
    components: { 
      NavBar,
      CartList,
      CartBottomBar,
      Scroll,
    
    },
    computed: {
      ...mapGetters(['cartLength'])
    },

    //添加商品后刷新重新计算滚动高度
    activated(){
      this.$refs.scroll.refresh()
    }
  }
</script>

<style scoped>
.cart{
  height: 100vh;
  position: relative;
}
.nav-bar{
  background-color: var(--color-tint);
  color: #fff;
}
.content{
  height: calc(100% - 133px);
  overflow: hidden;
}
 
</style>
