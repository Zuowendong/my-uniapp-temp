<template>
  <view class="wrapper-main">
    <view class="title">
      {{ title }}
      <text class="subtitle">{{ subtitle }}</text>
    </view>
    <slot></slot>
  </view>
</template>

<script>
export default {
  name: "WrapperBox",
  props: {
    title: {
      type: String,
      default: "",
    },
    subtitle: {
      type: String,
      default: "",
    },
  },
  data() {
    return {};
  },
  methods: {},
};
</script>

<style lang="scss" scoped>
.wrapper-main {
  background-color: #fff;
  padding: 20px;
  margin-bottom: 10px;
  .title {
    height: 40px;
    line-height: 40px;
    font-size: 16px;
    font-weight: 600;
    position: relative;
    padding-left: 10px;
    margin-bottom: 10px;
    &::before {
      position: absolute;
      top: 50%;
      left: 0;
      transform: translatey(-50%);
      content: "";
      width: 2px;
      height: 18px;
      background-color: #4a6ddb;
    }
    .subtitle {
      font-size: 14px;
      font-weight: normal;
      color: #ccc;
      padding-left: 4px;
    }
  }
}
</style>
