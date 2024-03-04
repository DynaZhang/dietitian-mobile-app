<template>
  <view class="upload-msg1-page">
    <view class="page-top">
      <view class="info-wrapper">
        <view class="user-avatar">
          <cover-image />
        </view>
        <view class="user-info">
          <view class="main-text">报考指导老师</view>
          <view class="desc-text">2023-04-13 发布</view>
        </view>
      </view>
      <view class="status-tag uploading">进行中</view>
    </view>
    <view class="form-wrapper">
      <view class="form-item">
        <view class="form-item__label">有效手机号</view>
        <view class="form-item__value">
          <uni-easyinput
            v-model="formData.phone"
            placeholder="请输入有效手机号"
          ></uni-easyinput>
        </view>
      </view>
      <view class="form-item">
        <view class="form-item__label">身份证正反面</view>
        <view class="form-item__value">
          <view class="idcard-wrapper">
            <view class="idcard-item">
              <view class="idcard-item__btn avatar">
                <cover-image
                  class="camera-icon"
                  src="../../static/icons/camera.png"
                />
              </view>
              <view class="idcard-item__label">人像面</view>
            </view>
            <view class="idcard-item">
              <view class="idcard-item__btn emblem">
                <cover-image
                  class="camera-icon"
                  src="../../static/icons/camera.png"
                />
              </view>
              <view class="idcard-item__label">国徽面</view>
            </view>
          </view>
        </view>
      </view>
      <view class="form-item">
        <view class="form-item__label">一寸白底照</view>
        <view class="form-item__value">
          <view class="white-hold">
            <view class="white-hold__btn">
              <cover-image
                class="camera-icon"
                src="../../static/icons/camera.png"
              />
            </view>
            <view class="white-hold__label"></view>
          </view>
        </view>
      </view>
    </view>
    <view class="next-step-btn">下一步</view>
  </view>
</template>

<script setup lang="ts">
import { ref } from "vue";

const formData = ref({
  phone: "",
});
</script>

<style lang="scss" scoped>
.upload-msg1-page {
  padding: 46rpx 30rpx;
  .page-top {
    display: flex;
    align-items: center;
    justify-content: space-between;
    .info-wrapper {
      display: flex;
      align-items: center;
      .user-avatar {
        margin-right: 20rpx;
        width: 60rpx;
        height: 60rpx;
        border-radius: 100%;
      }
      .user-info {
        .main-text {
          font-weight: 400;
          font-size: 28rpx;
          color: #242833;
          line-height: 28rpx;
        }
        .desc-text {
          font-weight: 400;
          font-size: 24rpx;
          color: #949699;
          line-height: 28rpx;
        }
      }
    }
    .status-tag {
      width: 90rpx;
      height: 32rpx;
      border-radius: 6rpx;
      font-weight: 400;
      font-size: 22rpx;
      line-height: 30rpx;
      text-align: center;
      &.uploading {
        color: #4ac2bf;
        border: 1rpx solid #4ac2bf;
      }
      &.ended {
        color: #b6b8bf;
        border: 1rpx solid #b6b8bf;
      }
    }
  }
  .form-wrapper {
    margin-top: 64rpx;
    .form-item {
      margin-bottom: 60rpx;
      &:last-child {
        margin-bottom: 0;
      }
      &__label {
        position: relative;
        height: 36rpx;
        font-weight: 600;
        font-size: 28rpx;
        line-height: 28rpx;
        color: #242833;
        letter-spacing: 1rpx;
        padding-left: 26rpx;
        margin-bottom: 30rpx;
        &::before {
          content: "";
          position: absolute;
          top: 0;
          left: 0;
          display: inline-block;
          width: 14rpx;
          height: 36rpx;
          background: #43b9a6;
          border-radius: 7rpx;
        }
      }
    }
  }
  .idcard-wrapper {
    display: flex;
    align-items: center;
    justify-content: space-between;
    .idcard-item {
      &__btn {
        display: flex;
        align-items: center;
        justify-content: center;
        width: 320rpx;
        height: 190rpx;
        margin-bottom: 12rpx;
        background-size: contain;
        background-repeat: no-repeat;
        cursor: pointer;
        &.avatar {
          background-image: url("../../static/icons/idcard-avatar.png");
        }
        &.emblem {
          background-image: url("../../static/icons/idcard-emblem.png");
        }
        .camera-icon {
          width: 80rpx;
          height: 80rpx;
        }
      }
      &__label {
        font-weight: 400;
        font-size: 24rpx;
        color: #666666;
        line-height: 33rpx;
        text-align: center;
      }
    }
  }
  .white-hold {
    &__btn {
      display: flex;
      align-items: center;
      justify-content: center;
      width: 206rpx;
      height: 268rpx;
      background-image: url("../../static/icons/whiteHold.png");
      background-size: contain;
      background-repeat: no-repeat;
      cursor: pointer;
      .camera-icon {
        width: 80rpx;
        height: 80rpx;
      }
    }
  }
  .next-step-btn {
    margin: 106rpx auto 0 auto;
    width: 438rpx;
    height: 94rpx;
    background: #4cd0ba;
    border-radius: 50rpx;
    font-weight: 500;
    font-size: 32rpx;
    color: #ffffff;
    line-height: 94rpx;
    text-align: center;
  }
}
</style>
