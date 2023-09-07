<template>
  <view class="main">
    <u-navbar title="楼盘详情">
      <view slot="left">
        <u-icon name="home" size="20"></u-icon>
      </view>
    </u-navbar>

    <view class="footerBox">
      <FooterBox />
    </view>
  </view>
</template>

<script>
import FooterBox from "./footer-box.vue";
export default {
  components: { FooterBox },
  data() {
    return {
      value6: 0,
    };
  },
  methods: {},
};
</script>

<style lang="scss">
.main {
  position: relative;

  .footerBox {
    position: fixed;
    bottom: 0;
    left: 0;
    width: 100%;
    height: 170px;
    box-shadow: 0 0 2px 1px rgba(77, 77, 77, 0.2);
  }
}
</style>
