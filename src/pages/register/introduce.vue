<template>
  <view class="introduce-page">
    <view class="card-item">
      <view class="card-title-wrapper">
        <text class="card-title-text">企评包过班和社评普通班的区别</text>
      </view>
      <view class="card-content">
        <view
          >企评包过班和社评普通班都会颁发国家人社部认证的证书，国网可查。二者全程都有录课辅导。</view
        >
        <view
          >企评包过班的认证主体是人社部认证的第三方企业，考试不过全额退款。</view
        >
        <view
          >社评普通班的认证主体是人社部认证的第三方社会组织，如团体、学校，考试不过需缴纳200左右的补考费下次补考。</view
        >
      </view>
    </view>
  </view>
</template>

<script setup lang="ts">
</script>

<style lang="scss" scoped>
.introduce-page {
  padding: 20rpx;
  .card-item {
    margin: 30rpx 0;
    .card-title-wrapper {
      background-color: #fff;
      background-image: url("../../static/icons/title.png");
      background-size: 50rpx 40rpx;
      background-repeat: no-repeat;
      overflow-y: hidden;
      .card-title-text {
        margin-top: 7rpx;
        margin-left: 14rpx;
        font-weight: bolder;
        font-size: 32rpx;
        color: #242833;
        line-height: 45rpx;
        letter-spacing: 2rpx;
      }
    }
    .card-content {
      margin-top: 30rpx;
      background: #ffffff;
      box-shadow: 0rpx 10rpx 40rpx -10rpx rgba(30, 37, 49, 0.1);
      border-radius: 20rpx;
      padding: 40rpx 50rpx;
      box-sizing: border-box;
      font-size: 26rpx;
      color: #242833;
    }
  }
}
</style>
