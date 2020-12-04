<template>
  <div class="bottom-bar">
    <div class="check-all">
      <check-button
        class="check-button"
        :is-checked="isSelectAll"
        @click.native="checkClick"
      />
      <span>全选</span>
    </div>
    <div class="price">合计：{{ totalPrice }}</div>
    <div class="caclculate" @click="calcClick">去计算({{ checkLength }})</div>
  </div>
</template>
<script>
import CheckButton from "components/content/checkButton/CheckButton.vue";

import { mapGetters } from "vuex";

export default {
  name: "CartBottomBar",
  components: {
    CheckButton,
  },
  computed: {
    ...mapGetters(["cartList"]),
    totalPrice() {
      return (
        " ¥" +
        this.cartList
          .filter((item) => {
            return item.checked;
          })
          .reduce((preValue, item) => {
            return preValue + item.price * item.count;
          }, 0)
          .toFixed(2)
      );
    },
    checkLength() {
      return this.cartList.filter((item) => item.checked).length;
    },
    //全选
    isSelectAll() {
      if (this.cartList.length === 0) return false;
      return !this.cartList.find((item) => !item.checked);
      // return !(this.cartList.filter(item => !item.checked).length)
    },
  },
  methods: {
    checkClick() {
      if (this.isSelectAll) {
        //全部选中
        this.cartList.forEach((item) => (item.checked = false));
      } else {
        //部分或全部不选中
        this.cartList.forEach((item) => (item.checked = true));
      }
    },
    calcClick(){
      if(!this.isSelectAll){
        this.$toast.show('请选择购买的商品')
      }
    }
  },
};
</script>
<style scoped>
.bottom-bar {
  position: relative;
  display: flex;
  font-size: 14px;
  height: 40px;
  line-height: 40px;
  background-color: #eee;
}
.check-all {
  width: 80px;
  display: flex;
  align-items: center;
}
.check-button {
  width: 20px;
  height: 20px;
  line-height: 20px;
  margin: 0 5px 0 10px;
}
.price {
  margin-left: 10px;
  flex: 1;
}
.caclculate {
  width: 90px;
  background-color: red;
  color: #fff;
  text-align: center;
}
</style>