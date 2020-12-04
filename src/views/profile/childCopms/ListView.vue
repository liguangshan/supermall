<template>
  <div id="listview">
    <div class="xiaoxi">
      <img src="~assets/img/profile/message.svg" alt="" />
      <span>我的消息</span>
    </div>
    <div class="xiaoxi">
      <img src="~assets/img/profile/pointer.svg" alt="" />
      <span>积分商城</span>
    </div>
    <div class="xiaoxi">
      <img src="~assets/img/profile/vip.svg" class="huiyuan" alt="" />
      <span>会员中心</span>
    </div>
    <div class="xiaoxi">
      <img src="~assets/img/profile/cart.svg" class="huiyuan" alt="" />
      <span>我的购物车</span>
    </div>
    <div class="xiaoxi">
      <img src="~assets/img/profile/shopping.svg" class="huiyuan" alt="" />
      <span>下载购物APP</span>
    </div>
    <div class="model">
      <div class="setIn">
        <img src="~assets/img/profile/shezhi.svg" alt="" />
        <span>设置</span>
      </div>
      <div class="setIn">
        <img src="~assets/img/profile/guanyu.svg" alt="" />
        <span>关于</span>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  name: "ListView",
  data() {
    return {};
  },
  methods: {},
};
</script>
<style scoped>
#listview {
  padding: 8px 5px 0 5px;
  border-top: solid 5px #f2f2f2;
  color: #666;
}
#listview img {
  width: 8%;
  height: 8%;
  margin-top: 15px;
}
.xiaoxi {
  position: relative;
  padding: 0 5px 2px 10px;
  border-bottom: solid 2px #f2f2f2;
}
.xiaoxi span {
  position: absolute;
  margin: 20px 0 0 20px;
  vertical-align: middle;
}
#listview .huiyuan {
  width: 9%;
  height: 9%;
  margin-right: -3px;
}
.setIn {
  position: relative;
  padding: 0 5px 2px 10px;
  border-bottom: solid 2px #f2f2f2;
}
.setIn span {
  position: absolute;
  margin: 20px 0 0 20px;
}
.model {
  margin-top: 15px;
}
</style>