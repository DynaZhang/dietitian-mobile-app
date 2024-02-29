<template>
  <view class="index-page">
    <view class="banner-wrapper"></view>
    <view class="content-wrapper">
      <view class="card-item">
        <view class="card-title-wrapper">
          <text class="card-title-text">报考相关</text>
        </view>
        <view class="card-content">
          <uni-segmented-control
            :current="currentTab"
            :values="items"
            style-type="text"
            active-color="#43B9A6"
            @clickItem="handleClickItem"
          />
          <view v-if="currentTab === 0" class="list-wrapper">
            <view class="list-item">第1步·选择学历水平</view>
            <view class="list-item">第2步·选择您的专业</view>
            <view class="list-item">第3步·选择年龄</view>
            <view class="list-item">第4步·选择目前的工作年限</view>
          </view>
          <view v-if="currentTab === 1" class="desc-wrapper">
            <view class="content">
              <text>营养师证书含金量</text>
              <view>
                <text>国家级技能等级证书，全国通用，国网可查</text>
                <text>招聘录用、考核晋升、评职加薪</text>
              </view>
            </view>
            <view class="content">
              <text>营养师就业直析</text>
              <view>
                <text>医院体检中心、护士行业</text>
                <text>养老院、保险公司健康评估</text>
                <text>社区卫生服务中心、健康管理中心顾问</text>
              </view>
            </view>
          </view>
          <view v-if="currentTab === 2" class="desc-wrapper">
            <view class="row-text">
              <text class="tag">选定班型</text>
              <text class="text">1.选定班型</text>
            </view>
            <view class="row-text">
              <text class="tag">签订合同</text>
              <text class="text">2.线上签订学习考证合同</text>
            </view>
            <view class="row-text">
              <text class="tag">交付学费</text>
              <text class="text">3.微信平台下单，对公账户安全有保障</text>
            </view>
            <view class="row-text">
              <text class="tag">学习考试</text>
              <text class="text">4.微信小程序实时跟进学习考试进度</text>
            </view>
          </view>
          <view class="regist-btn">马上报名</view>
        </view>
      </view>
      <view class="card-item">
        <view class="card-title-wrapper">
          <text class="card-title-text">常见问题</text>
        </view>
        <view class="card-content">
          <view class="list-wrapper">
            <view class="list-item">【就业】考上营养师证书就能找到工作吗</view>
            <view class="list-item"
              >【备考】备考多久能考上？我多久能拿证？</view
            >
            <view class="list-item">【备考】 2023年营养师考试科目及大纲</view>
            <view class="list-item">【材料】 2023年营养师报考准备材料</view>
          </view>
          <view class="load-more">
            <text>展开更多</text>
            <uni-icons type="down" size="18" />
          </view>
        </view>
      </view>
    </view>
  </view>
</template>

<script setup lang="ts">
import { ref } from "vue";

const currentTab = ref(0);
const items = ref(["报考指南", "就业流程", "报名流程"]);

const handleClickItem = (e: { currentIndex: number }) => {
  currentTab.value = e.currentIndex;
};
</script>

<style lang="scss" scoped>
@import "../../uni.scss";
.index-page {
  .banner-wrapper {
    width: 100%;
    height: 360rpx;
    background-image: url("../../static/icons/banner@2x.png");
    background-size: 100% 100%;
    background-repeat: no-repeat;
    .banner-title {
      font-weight: bolder;
      font-size: 50rpx;
      color: #040818;
      line-height: 60rpx;
      letter-spacing: 3rpx;
      text-align: left;
      font-style: normal;
    }
  }
  .content-wrapper {
    padding: 0 20rpx;
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
        box-shadow: 0px 10px 40px -10px rgba(30, 37, 49, 0.1);
        border-radius: 20px;
        border: 1px solid rgba(56, 56, 56, 0.07);
      }
    }
  }
}
</style>
