<template>
  <div class="container">
    <div class="tabs">
      <div
        :class="{'tab_active':item.isCheck}"
        class="tab_item"
        v-for="(item,index) in tabs"
        v-bind:key="index"
        @click="onChooseTabs(index)"
      >
        <div class="tab_key">{{item.key}}({{item.amount}})</div>
        <div class="actve_line"></div>
      </div>
    </div>
    <div class="coupons">
      <div class="coupon_item">
        <div class="coupon_top">
          <div class="coupon_top_left">
            <p class="price">
              <span class="rmb">￥</span>
              50
            </p>
            <div class="type">抵用卷</div>
          </div>
          <div class="coupon_top_right">
            <div class="coupon_name">穿啦进狗狗老火锅（传十点）等门店</div>
            <div class="coupon_time">有效期至：2019-03-28</div>
          </div>
        </div>
        <div class="coupon_bottom">美团APP用卷。满288可用、限最新版本客户端是用</div>
      </div>
    </div>
    <div class="get_coupons">零更多好卷</div>
  </div>
</template>
<script>
export default {
  data() {
    return {
      tabs: [
        {
          key: "带使用",
          amount: 1,
          isCheck: true
        },
        {
          key: "已使用",
          amount: 0,
          isCheck: false
        },
        {
          key: "已失效",
          amount: 5,
          isCheck: false
        }
      ]
    };
  },
  methods: {
    onChooseTabs(index) {
      for (let i in this.tabs) {
        if (this.tabs[i].isCheck) {
          this.tabs[i].isCheck = false;
        }
      }
      this.tabs[index].isCheck = true;
    }
  }
};
</script>
<style scoped>
.container {
  width: 100%;
  height: 100vh;
  background: #f1f1f1;
  display: flex;
  flex-direction: column;
}
.tabs {
  display: flex;
  justify-content: space-around;
  font-size: 24rpx;
  color: #00f1f1;
  height: 50rpx;
  padding: 16rpx;
  background: white;
}
.tab_active {
  color: black;
  font-weight: bold;
}
.tab_active .actve_line {
  width: 50%;
  margin: 0 auto;
  height: 4rpx;
  background: #f1f100;
  margin-top: 10rpx;
  border-radius: 50%;
}
.get_coupons {
  height: 70rpx;
  background: white;
  text-align: center;
  font-size: 24rpx;
  color: aqua;
  line-height: 70rpx;
}
.coupons {
  flex: 1;
  padding: 32rpx;
}
.coupon_item{
    border-radius: 16rpx;
    box-shadow: 2rpx 2rpx 4rpx #666;
}
.coupon_top{
    display: flex;
}
.coupon_top_left{
    width: 150rpx;
    height: 150rpx;
    background: orange;
    color: white;
}
.coupon_bottom{
    background: #f1f1f1;
    padding: 16rpx;
    color: #333;
    font-size: 24rpx;
}
</style>


