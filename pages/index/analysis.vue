<template>
  <view class="analysisWrapper">
    <view class="box">
      <view class="title">楼盘分析报告</view>
      <view class="subtitle">点击获取更多楼盘详细信息 -></view>
    </view>
  </view>
</template>

<script>
export default {
  data() {
    return {};
  },
  methods: {},
};
</script>

<style lang="scss">
.analysisWrapper {
  background-color: #fff;
  padding: 10px 15px;
  margin-bottom: 10px;
  .box {
    height: 110px;
    background-color: #2979ff;
    border-radius: 10px;
    color: #fff;
    display: flex;
    flex-direction: column;
    justify-content: center;
    padding-left: 20px;
    .title {
      font-size: 22px;
      font-weight: bold;
      padding-bottom: 15px;
    }
  }
}
</style>
