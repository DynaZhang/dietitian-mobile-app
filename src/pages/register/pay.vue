<template>
  <view class="pay-page">
    <view class="content-box">
      <view class="title-wrapper">
        <text class="title-text">报名班型</text>
        <view class="introduce-wrapper">
          <cover-image class="question-icon" :src="questionIcon" />
          <text class="introduce-text">班型详细介绍</text>
        </view>
      </view>
      <view class="card-wrapper">
        <view class="card-item green selected">
          <text class="card-title">企评保过班</text>
          <text class="price">
            <text class="per">¥</text>
            <text class="value">5000</text>
          </text>
          <text class="card-desc">承诺考试不过直接退款</text>
        </view>
        <view class="card-item blue">
          <text class="card-title">社评普通班</text>
          <text class="price">
            <text class="per">¥</text>
            <text class="value">4888</text>
          </text>
          <text class="card-desc">考试不过需缴纳补考费</text>
        </view>
      </view>
    </view>
    <view class="content-box">
      <view class="title-wrapper">
        <text class="title-text">个人信息</text>
        <view class="introduce-wrapper">
          <text class="link-text">
            修改个人信息
            <uni-icons type="right" size="18" color="#43b9a6"></uni-icons>
          </text>
        </view>
      </view>
      <view class="list-wrapper">
        <view class="row">
          <text class="row-label">学历水平：</text>
          <text class="row-value">大专</text>
        </view>
        <view class="row">
          <text class="row-label">专业：</text>
          <text class="row-value">非医药卫生专业</text>
        </view>
        <view class="row">
          <text class="row-label">工作年限：</text>
          <text class="row-value">应届毕业生</text>
        </view>
        <view class="row">
          <text class="row-label">年龄：</text>
          <text class="row-value">26周岁</text>
        </view>
      </view>
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
    <view class="footer-wrapper">
      <view class="agreement-wrapper">
        <view class="checkbox selected"></view>
        <view class="desc-text">
          我已阅读 <text class="link-text">《健康管理师培训合同》</text> 并同意
        </view>
      </view>
      <view class="cart-wrapper">
        <view class="price-text">¥5000</view>
        <view class="regist-btn" @click="handleRegister">立即报名</view>
      </view>
    </view>
    <popup :show="showPaySuccessPopup">
      <view class="popup-content">
        <view class="title-wrapper">支付完成，请上传报考资料</view>
        <view class="desc-text"
          >请上传报名所需材料，如暂时不方便操作，晚些可在首页底部进入“上传”页面操作</view
        >
        <view class="popup-footer">
          <view class="default-btn" @click="handleClosePopup">晚些上传</view>
          <view class="primary-btn" @click="handleGotoUpload">立即上传</view>
        </view>
      </view>
    </popup>
  </view>
</template>

<script setup lang="ts">
import { defineComponent, ref } from "vue";
import questionIcon from "../../static/icons/question.png";
import Popup from "../../components/popup/index.vue";

const showPaySuccessPopup = ref<boolean>(false);
const handleRegister = () => {
    showPaySuccessPopup.value = true;
}
const handleClosePopup = () => {
    showPaySuccessPopup.value = false;
}
const handleGotoUpload = () => {
    handleClosePopup();
}
</script>

<style lang="scss" scoped>
.pay-page {
  padding: 32rpx;
  .content-box {
    margin-bottom: 30rpx;
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
  .footer-wrapper {
    position: fixed;
    bottom: 0;
    left: 0;
    right: 0;
    height: 224rpx;
    z-index: 9999;
    .agreement-wrapper {
      padding: 30rpx 40rpx;
      display: flex;
      align-items: center;
      height: 100rpx;
      background: #e8fdf4;
      box-sizing: border-box;
      .checkbox {
        width: 32rpx;
        height: 32rpx;
        margin-right: 30rpx;
        background-size: contain;
        background-repeat: no-repeat;
        &.unselected {
          background-image: url("../../static/icons/unselected.png");
        }
        &.selected {
          background-image: url("../../static/icons/selected.png");
        }
      }
      .link-text {
        font-weight: 400;
        font-size: 28rpx;
        color: #000000;
        line-height: 28rpx;
        color: #42b8a5;
      }
    }
    .cart-wrapper {
      display: flex;
      align-items: center;
      justify-content: space-between;
      padding: 20rpx 40rpx;
      box-sizing: border-box;
      background-color: #ffffff;
      .price-text {
        font-weight: 500;
        font-size: 34rpx;
        color: #42b8a5;
        line-height: 34rpx;
      }
      .regist-btn {
        width: 240rpx;
        height: 90rpx;
        line-height: 90rpx;
        background: #4cd0ba;
        border-radius: 50rpx;
        font-weight: 500;
        font-size: 32rpx;
        color: #ffffff;
        text-align: center;
        cursor: pointer;
      }
    }
  }
  .popup-content {
    width: 656rpx;
    height: 430rpx;
    padding: 60rpx 50rpx;
    box-sizing: border-box;
    .title-wrapper {
      margin-bottom: 30rpx;
      font-weight: 600;
      font-size: 36rpx;
      color: #201f31;
      letter-spacing: 2rpx;
    }
    .desc-text {
        margin-bottom: 60rpx;
        font-weight: 400;
        font-size: 28rpx;
        color: #666666;
    }
    .popup-footer {
        display: flex;
        align-items: center;
        justify-content: space-between;
        .default-btn {
            width: 248rpx;
            height: 94rpx;
            font-size: 32rpx;
            color: #43B9A6;
            line-height: 94rpx;
            text-align: center;
            border: 2rpx solid #43B9A6;
            border-radius: 50rpx;
            cursor: pointer;
        }
        .primary-btn {
            width: 248rpx;
            height: 94rpx;
            font-size: 32rpx;
            background-color: #43B9A6;
            color: #ffffff;
            line-height: 94rpx;
            text-align: center;
            border-radius: 50rpx;
            cursor: pointer;
        }
    }
  }
}
</style>
