<template>
  <view class="agreement-page">
    <view class="card-item">
      <view class="card-title-wrapper">
        <text class="card-title-text">用户协议</text>
      </view>
      <view class="card-content">
        <view>
          <view>甲方(培训单位): </view>
          <view>乙方(委托培训单位): </view>
          <view>丙方(学生):</view>
          <view>为了开牌人才培训的渠道，加速智力开发，保证受培人员的质量，明确培训各方的责任，为社会提
          供更多更好的人才，经甲乙、丙三方协商一致，特订立本合同，以便共同遵守。</view>
          <view>第一条</view>
          <view>甲方对丙方的授课内容，应按照教育部对同类本科生(或大专、中专生)所规定(部属学校按其系
          统的有关规定)的移目、学时实排，不得降低对方的要求。甲方对内方在校期间的德、智、休发展情
          况，应于每学期末向乙方作一次详细介绍。</view>
          <view>第二条</view>
          <view>甲方如发现丙方有违反校纪校规的行为，应及时与乙方取得联系，共同研究处理办法。丙方在期末
          思想品德评为“差”等、学期内有三门功课不及格，一年之内有两门功课补考不及格者，甲方有权劝其退
          学或取消其学籍。</view>
          <view>第三条</view>
          <view>甲方负责丙方奖学金的评定和发放。奖学金每学期评定一次，分一、二、三等，具体评定和发放方法、标准，按甲方的统一规定办理。</view>
          <view>第四条</view>
          <view>乙方承担丙方在校学习期间的全部学费和奖学金费。学费每人每学期元，其他费用每人每学期元。丙方的以上费用，乙方应于每学期学生报到时直接汇到甲方，或由丙方带交给甲方。</view>
          <view>第五条</view>
          <view>乙方应按规定发给丙方工资(标准工资加地区生活费补贴，不发奖金)和其他福利待遇，丙方如在
          甲方食宿。7方按规定每天补助丙方生活费元(如国家有新规定，按新规定执行)，向甲方支
          对丙方的寄宿弗和代伙器。内方节假日回家的来回路费，7方按规定给予报销。内方如不在甲方住宿
          其家离甲方两公里以上，乙方应按国家规定按月发给交通费补贴。</view>
          <view>第六条</view>
          <view>乙方要加强对丙方的管理和教育，要经常了解丙方的学习和思想品德状况，如发现丙方有问题，应及时配合甲方教育和处理。</view>
          <view>第七条</view>
          <view>丙方学习结束，经甲方考核、考试合格准予毕业后，乙方应根据丙方所学专业和甲方提供的丙方德、智、体发展情况，合理安排其工作。</view>
        </view>
      </view>
    </view>
  </view>
</template>

<script setup lang="ts">
</script>

<style lang="scss" scoped>
.agreement-page {
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
