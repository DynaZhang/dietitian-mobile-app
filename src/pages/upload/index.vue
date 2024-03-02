<template>
  <view class="upload-page">
    <view class="content-box">
      <view class="title-wrapper">
        <text class="title-text">订单信息</text>
      </view>
      <view class="card-wrapper">
        <view class="card-top">
          <view class="info-wrapper">
            <view class="user-avatar">
              <cover-image :src="iconMap.upload" />
            </view>
            <view class="user-info">
              <view class="main-text">报考指导老师</view>
              <view class="desc-text">2023-04-13 发布</view>
            </view>
          </view>
          <view class="status-tag uploading">进行中</view>
        </view>
        <view class="card-content">
          <view class="main-text">请上传详细报名信息</view>
          <view class="desc-text">请上传免冠照等</view>
        </view>
        <view class="card-bottom">
          <view class="upload-status">
            <view class="status-icon"
              ><cover-image :src="iconMap.upload"
            /></view>
            <text class="main-text">信息已上传 核验中</text>
          </view>
          <view class="desc-text">信息已上传</view>
        </view>
      </view>
    </view>
  </view>
</template>

<script setup lang="ts">
import { ref } from "vue";
import uploadIcon from "../../static/icons/upload.png";
import uploadingIcon from "../../static/icons/uploading.png";
import uploadSuccessIcon from "../../static/icons/uploadSuccess.png";
import uploadFailIcon from "../../static/icons/uploadFail.png";

const iconMap = ref({
  upload: uploadIcon,
  uploading: uploadingIcon,
  success: uploadSuccessIcon,
  fail: uploadFailIcon,
});
</script>

<style lang="scss" scoped>
.upload-page {
  padding: 30rpx 20rpx;
  .content-box {
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
    }
    .card-wrapper {
      margin-top: 30rpx;
      padding: 40rpx;
      box-sizing: border-box;
      background: #ffffff;
      box-shadow: 0rpx 10rpx 40rpx -10rpx rgba(30, 37, 49, 0.1);
      border-radius: 20rpx;
      border: 1rpx solid rgba(56, 56, 56, 0.07);
      .card-top {
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
      .card-content {
        margin-top: 32rpx;
        .main-text {
          font-size: 32rpx;
          color: #242833;
          letter-spacing: 1rpx;
        }
        .desc-text {
          font-size: 28rpx;
          color: #949699;
          letter-spacing: 1rpx;
        }
      }
      .card-bottom {
        margin-top: 32rpx;
        padding: 30rpx;
        box-sizing: border-box;
        background: #fdfdfd;
        border-radius: 8rpx;
        border: 1rpx solid #e8e8eb;
        .upload-status {
          display: flex;
          align-items: center;
          justify-content: center;
          border-bottom: 1rpx solid #e3e3e8;
          padding-bottom: 26rpx;
          .status-icon {
            width: 34rpx;
            height: 34rpx;
            margin-right: 20rpx;
          }
          .main-text {
            font-weight: 400;
            font-size: 28rpx;
            color: #242833;
          }
        }
        .desc-text {
          margin-top: 20rpx;
          font-weight: 400;
          font-size: 28rpx;
          color: #949699;
          text-align: center;
        }
      }
    }
  }
}
</style>
