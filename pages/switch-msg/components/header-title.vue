<template>
  <view class="header">
    <view class="header-title">
      <text class="title">东岸观邸-云尚丹霞</text>
      <u-tag text="在售" size="mini"></u-tag>
    </view>
    <view class="header-subtitle">
      <u-icon name="map" color="#f29100" size="20"></u-icon>
      <text class="text">1.5容积率，滨水环河宽景，城市界面升级</text>
    </view>
  </view>
</template>

<script>
export default {
  name: "HeaderTitle",
  data() {
    return {};
  },
  methods: {},
};
</script>

<style lang="scss">
.header {
  &-title {
    display: flex;
    align-items: center;
    font-size: 22px;
    font-weight: bold;
    margin-bottom: 10px;
    .title {
      margin-right: 10px;
    }
  }
  &-subtitle {
    display: flex;
    align-items: center;
    color: #f29100;
    font-size: 14px;
    .text {
      margin-left: 10px;
    }
  }
}
</style>
