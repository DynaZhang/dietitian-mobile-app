<template>
  <view class="login-page">
    <cover-image class="login-logo" :src="logoIcon" />
    <view class="message-wrapper"> </view>
    <view class="login-btn">微信登录</view>
    <view class="login-agreement" @click="handleSelect">
      <cover-image
        class="select-icon"
        :src="isSelected ? selectedIcon : unSelectedIcon"
      />
      <view class="label">我已同意</view>
      <view class="link-text">《用户协议》</view>
    </view>
  </view>
</template>

<script setup lang="ts">
import { ref } from "vue";
import logoIcon from "../../static/icons/logo.png";
import selectedIcon from "../../static/icons/selected.png";
import unSelectedIcon from "../../static/icons/unSelected.png";

const isSelected = ref<boolean>(false);
const handleSelect = () => {
  isSelected.value = !isSelected.value;
};
</script>

<style lang="scss" scoped>
.login-page {
  .login-logo {
    margin: 324rpx auto 633rpx auto;
    width: 528rpx;
    height: 86rpx;
  }
  .login-btn {
    margin: 0 auto 92rpx auto;
    width: 686rpx;
    height: 100rpx;
    background: #4cd0ba;
    border-radius: 50rpx;
    font-weight: 500;
    font-size: 32rpx;
    color: #ffffff;
    line-height: 100rpx;
    text-align: center;
  }
  .login-agreement {
    display: flex;
    justify-content: center;
    align-items: center;
    cursor: pointer;
    .select-icon {
      display: inline-block;
      width: 30rpx;
      height: 30rpx;
    }
    .label {
      margin-left: 16rpx;
      color: #c5c8ce;
      font-size: 24rpx;
    }
    .link-text {
      color: #43b9a6;
      font-size: 24rpx;
    }
  }
}
</style>
