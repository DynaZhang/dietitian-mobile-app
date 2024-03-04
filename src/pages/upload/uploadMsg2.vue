<template>
  <view class="upload-msg2-page">
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
        <view class="form-item__label">学历水平</view>
        <view class="form-item__value">
          <uni-data-select
            v-model="formData.career"
            :localdata="careerData"
            placeholder="请选择您的最高学历"
          ></uni-data-select>
        </view>
      </view>
      <view class="form-item">
        <view class="form-item__label">
          <text>学信网备案</text>
          <text class="link-text">如何获得学信网报告？</text>
        </view>
        <view class="form-item__value">
          <uni-file-picker
            ref="files"
            file-mediatype="all"
            file-extname="pdf"
            :auto-upload="false"
          >
            <view class="upload-button">
              <text>请上传学信网备案表</text>
            </view>
          </uni-file-picker>
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

<script lang="ts" setup>
import { ref } from "vue";

const formData = ref({
  phone: "",
  career: "",
});
const careerData = ref([
  { value: 0, text: "研究生及以上" },
  { value: 1, text: "本科" },
  { value: 2, text: "专科" },
  { value: 3, text: "高中/中专" },
]);
</script>

<style lang="scss" scoped>
.upload-msg2-page {
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
        display: flex;
        align-items: center;
        justify-content: space-between;
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
        .link-text {
          font-weight: 400;
          font-size: 26rpx;
          color: #43b9a6;
          cursor: pointer;
        }
      }
    }
  }
  .upload-button {
    padding: 30rpx 18rpx;
    box-sizing: border-box;
    height: 100rpx;
    background: #ffffff;
    border-radius: 12rpx;
    border: 2rpx solid #e7e7e7;
    font-weight: 400;
    font-size: 28rpx;
    color: #a6a8aa;
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
