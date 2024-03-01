<template>
  <view class="login-fail-page">
    <text class="result-text">经查询，您还不满足报考条件</text>
    <view class="reason-wrapper">
      <view v-for="item in reasonList" :key="item.id" class="reason-item">
        <text class="reason-tag">{{ item.title }}</text>
        <text class="reason-desc">{{ item.desc }}</text>
      </view>
      <view class="refill-btn">重新填写</view>
    </view>
  </view>
</template>

<script setup lang="ts">
import { ref } from "vue";
const reasonList = ref([
  {
    id: 1,
    title: "年龄要求",
    desc: "年龄需满24周岁",
  },
  {
    id: 2,
    title: "学历要求",
    desc: "需拿到高中（或同等学力）有效毕业证书",
  },
]);
</script>

<style lang="scss" scoped>
.login-fail-page {
  width: 100vw;
  height: 100vh;
  background-image: url("../../static/icons/loginFailBg.png");
  background-size: contain;
  background-repeat: no-repeat;
  .result-text {
    display: block;
    padding-top: 240rpx;
    height: 65rpx;
    font-weight: 600;
    font-size: 46rpx;
    color: #43b9a6;
    line-height: 65rpx;
    text-align: center;
  }
  .reason-wrapper {
    width: 656rpx;
    height: 642rpx;
    margin: 60rpx auto 0 auto;
    padding: 200rpx 50rpx 0 50rpx;
    background-image: url("../../static/icons/reasonBg.png");
    background-size: contain;
    background-repeat: no-repeat;
    box-sizing: border-box;
    .reason-item {
      display: flex;
      align-items: center;
      margin-bottom: 30rpx;
      &:last-child {
        margin-bottom: 0;
      }
      .reason-tag {
        width: 104rpx;
        height: 33rpx;
        background: #8fd5ca;
        border-radius: 4rpx;
        font-weight: 600;
        font-size: 21rpx;
        color: #343434;
        line-height: 33rpx;
        text-align: center;
        font-style: normal;
      }
      .reason-desc {
        margin-left: 20rpx;
        font-weight: 500;
        font-size: 24rpx;
        color: #343434;
        line-height: 33rpx;
        text-align: left;
        font-style: normal;
      }
    }
  }
  .refill-btn {
    margin: 85rpx auto 0 auto;
    width: 400rpx;
    height: 90rpx;
    background: #4cd0ba;
    border-radius: 50rpx;
    font-weight: 500;
    font-size: 32rpx;
    color: #ffffff;
    line-height: 90rpx;
    text-align: center;
  }
}
</style>
