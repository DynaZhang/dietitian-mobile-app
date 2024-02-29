<template>
  <view class="register-page">
    <view class="card-item">
      <view class="card-title-wrapper">
        <text class="card-title-text">报名检查</text>
        <text class="card-title-desc">承诺信息仅用于报名通知，安全不泄露</text>
      </view>
      <view class="card-content">
        <uni-forms :modelValue="formData" label-position="top">
          <uni-forms-item label="1.请填写手机号" name="phone" label-width="110">
            <uni-easyinput
              type="text"
              v-model="formData.name"
              placeholder="请填写有效手机号，仅用于报名通知"
            />
          </uni-forms-item>
          <uni-forms-item label="2.请输入年龄" name="age" label-width="110">
            <uni-easyinput
              type="number"
              v-model="formData.age"
              placeholder="请填写当前年龄"
            />
          </uni-forms-item>
          <uni-forms-item
            name="hobby"
            label="3.请选择学历水平"
            label-width="110"
          >
            <uni-data-checkbox
              v-model="formData.career"
              :localdata="careerData"
            />
          </uni-forms-item>
          <uni-forms-item
            name="hobby"
            label="4.请选择您的专业"
            label-width="110"
          >
            <uni-data-checkbox
              v-model="formData.profession"
              :localdata="professionData"
            />
          </uni-forms-item>
          <uni-forms-item
            name="hobby"
            label="5.请选择目前的工作年限"
            label-width="110"
          >
            <uni-data-checkbox
              v-model="formData.workCareer"
              :localdata="workCareerData"
            />
          </uni-forms-item>
        </uni-forms>
        <view class="register-btn">报名检查</view>
      </view>
    </view>
  </view>
</template>

<script setup lang="ts">
import { ref } from "vue";
const formData = ref({
  name: "",
  age: "",
  career: "",
  profession: "",
  workCareer: "",
});
const careerData = ref([
  {
    text: "高中/中专",
    value: 0,
  },
  {
    text: "本科",
    value: 1,
  },
  {
    text: "专科",
    value: 2,
  },
  {
    text: "研究生及以上",
    value: 3,
  },
]);
const professionData = ref([
  {
    text: "医药卫生专业",
    value: 0,
  },
  {
    text: "非医药卫生专业",
    value: 1,
  },
]);
const workCareerData = ref([
  {
    text: "应届/无经验",
    value: 0,
  },
  {
    text: "3-5年",
    value: 1,
  },
  {
    text: "0-3年",
    value: 2,
  },
  {
    text: "5年以上",
    value: 3,
  },
]);
</script>

<style lang="scss" scoped>
.register-page {
  padding: 34rpx;
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
      .card-title-desc {
        margin-left: 16rpx;
        font-weight: 400;
        font-size: 24rpx;
        color: #acacac;
        line-height: 36rpx;
        text-align: left;
        font-style: normal;
      }
    }
    .card-content {
      margin-top: 60rpx;
    }
    .register-btn {
      width: 400rpx;
      height: 90rpx;
      margin: 180rpx auto 0 auto;
      background: #4cd0ba;
      border-radius: 50rpx;
      font-weight: 500;
      font-size: 32rpx;
      color: #ffffff;
      line-height: 90rpx;
      text-align: center;
    }
  }
}
</style>
