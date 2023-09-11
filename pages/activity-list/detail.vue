<template>
  <view class="activityDetail">
    <view class="title">东岸国际社区大势崛起</view>
    <view class="time">2023-09-10发布</view>
    <view class="content">
      #东岸国际社区大势崛起40座公园1口座城川沙向东，生活赋新一东岸观邸建面约83-155m精装洋房&高层
    </view>
    <view class="img">
      <u--image :src="url" width="100%" mode="aspectFit" radius="6"></u--image>
    </view>
  </view>
</template>

<script>
export default {
  data() {
    return {
      url: "https://raw.githubusercontent.com/Zuowendong/autocommit-robot/master/pictures/2023-8-30.png",
    };
  },
  methods: {},
};
</script>

<style lang="scss">
.activityDetail {
  padding: 16px;
  .title {
    font-size: 18px;
    font-weight: 500;
  }
  .time {
    font-size: 13px;
    color: #ccc;
    padding: 14px 0 20px 0;
  }
  .content {
    line-height: 30px;
    font-size: 15px;
    margin-bottom: 20px;
  }
}
</style>
