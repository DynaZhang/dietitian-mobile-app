<template>
  <view class="wait-pay-page">
    <view class="remain-time-wrapper">
      <view class="desc-text">支付剩余时间</view>
      <view class="remain-time">14:26:00</view>
    </view>
    <view class="content-box">
      <view class="title-wrapper">
        <text class="title-text">订单信息</text>
      </view>
      <view class="list-wrapper">
        <view class="row">
          <text class="row-label">服务内容：</text>
          <text class="row-value">健康管理师资格证（三级）</text>
        </view>
        <view class="row">
          <text class="row-label">收款主体：</text>
          <text class="row-value">北京知诚教育有限责任公司</text>
        </view>
        <view class="row">
          <text class="row-label">订单编号：</text>
          <text class="row-value">786786856567565</text>
        </view>
        <view class="row">
          <text class="row-label">总计价格：</text>
          <text class="row-value price">￥5000</text>
        </view>
      </view>
    </view>
    <view class="need-pay-wrapper">
      <text class="desc">需支付</text>
      <text class="value">¥3999</text>
    </view>
    <view class="footer-wrapper">
      <view class="cart-wrapper">
        <view class="price-text">
          <text class="fact-value">¥3999</text>
          <text class="pre-value">¥5000</text>
        </view>
        <view class="btn-group" @click="handleRegister">
          <view class="cancel-btn">取消报名</view>
          <view class="regist-btn">立即报名</view>
        </view>
      </view>
    </view>
  </view>
</template>

<script setup lang="ts">
import { ref, onMounted } from "vue";
const remainTime = ref<number>(0);
</script>

<style lang="scss" scoped>
.wait-pay-page {
  .remain-time-wrapper {
    background-color: #fff;
    height: 180rpx;
    padding: 32rpx;
    box-sizing: border-box;
    .desc-text {
      margin-bottom: 12rpx;
      font-weight: 400;
      font-size: 24rpx;
      color: #262626;
      text-align: center;
    }
    .remain-time {
      font-weight: 500;
      font-size: 60rpx;
      color: #43b9a6;
      text-align: center;
    }
  }
  .content-box {
    margin: 30rpx 0;
    padding: 32rpx;
    box-sizing: border-box;
    .title-wrapper {
      display: flex;
      align-items: center;
      justify-content: space-between;
      margin-bottom: 30rpx;
      background-color: #fff;
      background-image: url("../../static/icons/title.png");
      background-size: 50rpx 40rpx;
      background-repeat: no-repeat;
      overflow-y: hidden;
      .title-text {
        margin-top: 7rpx;
        margin-left: 14rpx;
        font-weight: bolder;
        font-size: 32rpx;
        color: #242833;
        line-height: 45rpx;
        letter-spacing: 2rpx;
      }
      .introduce-wrapper {
        display: flex;
        align-items: center;
        cursor: pointer;
        .question-icon {
          width: 32rpx;
          height: 32rpx;
          margin-right: 3rpx;
        }
        .introduce-text {
          font-size: 28rpx;
          color: #949699;
          line-height: 40rpx;
          letter-spacing: 1px;
        }
        .link-text {
          display: flex;
          align-items: center;
          font-weight: 400;
          font-size: 28rpx;
          color: #43b9a6;
          line-height: 28rpx;
          cursor: pointer;
        }
      }
    }
    .card-wrapper {
      display: flex;
      justify-content: space-between;
      .card-item {
        position: relative;
        width: 334rpx;
        height: 200rpx;
        background-size: contain;
        background-repeat: no-repeat;
        padding: 37rpx 32rpx;
        box-sizing: border-box;
        &.green {
          margin-right: 25rpx;
          background-image: url("../../static/icons/greenBg.png");
          &.selected {
            background-image: url("../../static/icons/greenSelectedBg.png");
            &::after {
              content: "";
              position: absolute;
              top: 0;
              right: 0;
              width: 86rpx;
              height: 74rpx;
              background-image: url("../../static/icons/greenBadge.png");
              background-size: contain;
              background-repeat: no-repeat;
            }
          }
        }
        &.blue {
          background-image: url("../../static/icons/blueBg.png");
          &.selected {
            background-image: url("../../static/icons/blueSelectedBg.png");
            &::after {
              content: "";
              position: absolute;
              top: 0;
              right: 0;
              width: 86rpx;
              height: 74rpx;
              background-image: url("../../static/icons/blueBadge.png");
              background-size: contain;
              background-repeat: no-repeat;
            }
          }
        }
        .card-title {
          display: block;
          font-weight: 600;
          font-size: 32rpx;
          color: #ffffff;
          line-height: 32rpx;
          text-shadow: 0rpx 2rpx 13rpx rgba(0, 0, 0, 0.17);
        }
        .price {
          display: block;
          margin-top: 26rpx;
          .per {
            font-weight: 400;
            font-size: 24rpx;
            color: #ffffff;
            line-height: 24rpx;
            text-shadow: 0rpx 2rpx 13rpx rgba(0, 0, 0, 0.17);
          }
          .value {
            font-weight: 600;
            font-size: 34rpx;
            color: #ffffff;
            line-height: 34rpx;
            text-shadow: 0rpx 2rpx 13rpx rgba(0, 0, 0, 0.17);
          }
        }
        .card-desc {
          display: block;
          margin-top: 18rpx;
          font-weight: 400;
          font-size: 26rpx;
          color: #ffffff;
          line-height: 26rpx;
          text-shadow: 0rpx 2rpx 13rpx rgba(0, 0, 0, 0.17);
        }
      }
    }
    .list-wrapper {
      .row {
        display: flex;
        margin-bottom: 20rpx;
        &:last-child {
          margin-bottom: 0;
        }
        &-label {
          display: inline-block;
          width: 160rpx;
          font-weight: 400;
          font-size: 28rpx;
          color: #999999;
          line-height: 28rpx;
        }
        &-value {
          font-weight: 400;
          font-size: 28rpx;
          color: #242833;
          line-height: 28rpx;
          &.price {
            color: #fe6710;
          }
        }
      }
    }
  }
  .need-pay-wrapper {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 28rpx 32rpx;
    box-sizing: border-box;
    .desc {
      font-weight: 400;
      font-size: 28rpx;
      color: #999999;
    }
    .value {
      font-weight: 500;
      font-size: 28rpx;
      color: #fe6710;
    }
  }
  .footer-wrapper {
    position: fixed;
    bottom: 0;
    left: 0;
    right: 0;
    height: 124rpx;
    z-index: 9999;
    .cart-wrapper {
      display: flex;
      align-items: center;
      justify-content: space-between;
      padding: 20rpx 40rpx;
      box-sizing: border-box;
      background-color: #ffffff;
      .price-text {
        .fact-value {
          margin-right: 24rpx;
          font-weight: 500;
          font-size: 34rpx;
          color: #42b8a5;
        }
        .pre-value {
          font-weight: 400;
          font-size: 26rpx;
          color: #8c919d;
          text-decoration: line-through;
        }
      }
      .btn-group {
        display: flex;
        align-items: center;
        height: 90rpx;
        cursor: pointer;
        .cancel-btn {
            padding: 30rpx;
            box-sizing: border-box;
            height: 100%;
          background: #e8fdf4;
          font-weight: 500;
          font-size: 32rpx;
          color: #4cd0ba;
          line-height: 30rpx;
          text-align: center;
          border-radius: 50rpx 0rpx 0rpx 50rpx;
        }
        .regist-btn {
            padding: 30rpx;
            box-sizing: border-box;
            height: 100%;
          background: #4cd0ba;
          font-weight: 500;
          font-size: 32rpx;
          color: #ffffff;
          line-height: 30rpx;
          text-align: center;
          border-radius: 0px 50rpx 50rpx 0px;
        }
      }
    }
  }
}
</style>