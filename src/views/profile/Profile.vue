<template>
  <div class="profile">
    
    <nav-bar class="pro-nav">
      <div slot="center">个人中心</div>
    </nav-bar>
    
    <scroll class="content" ref="scroll">
      <users />
      <section class="account">
        <div class="account-item">
          <div class="number"><span class="balance">0.00</span>元</div>
          <div class="account-info">我的余额</div>
        </div>
        <div class="account-item">
          <div class="number"><span class="balance">0</span>个</div>
          <div class="account-info">我的优惠</div>
        </div>
        <div class="account-item">
          <div class="number"><span class="balance">0</span>分</div>
          <div class="account-info">我的积分</div>
        </div>
      </section>

      <list-view />
      <div class="bottom"></div>
    </scroll>
  </div>
</template>

<script>
import ListView from "./childCopms/ListView.vue";
import Users from "./childCopms/Users.vue";
import NavBar from "components/common/navbar/NavBar";
import Scroll from "../../components/common/scroll/Scroll.vue";

export default {
  name: "Profile",
  components: {
    ListView,
    Users,
    NavBar,
    Scroll,
  },
};
</script>

<style scoped>
.profile {
  height: 100vh;
  position: relative;
}
.content {
  position: absolute;

  height: calc(100% - 93px);
  overflow: hidden;
}
.pro-nav {
  background-color: var(--color-tint);
  color: #fff;
  box-shadow: 0 2px 1px rgba(100, 100, 100, 0.05);
}
.account {
  display: flex;
  padding: 4px 0;
}
.account :last-child {
  border-right: solid 1px #fff;
}
.account-item {
  width: 100%;
  background-color: #fff;
  text-align: center;
  font-size: 14px;
  padding: 15px;
  border-right: solid 1px #f2f2f2;
  color: #666;
}
.account-item .balance {
  font-size: 24px;
  font-weight: 700;
  color: #ff5f3e;
}
.account-info {
  margin-top: 6px;
}
.bottom {
  width: 100%;
  height: 210px;
}
</style>
