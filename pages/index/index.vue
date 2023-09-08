<template>
  <view class="main">
    <u-navbar title="uniapp">
      <view slot="left">
        <u-icon name="home" size="20"></u-icon>
      </view>
    </u-navbar>
    <SwiperList />
    <SwitchMsg />
    <view class="footerBox">
      <FooterBox />
    </view>
  </view>
</template>

<script>
import SwiperList from "../swiper-list/index.vue";
import SwitchMsg from "../switch-msg/index.vue";
import FooterBox from "./footer-box.vue";
export default {
  components: { SwiperList, SwitchMsg, FooterBox },
  data() {
    return {};
  },
  methods: {},
};
</script>

<style lang="scss">
.main {
  position: relative;
  padding-bottom: 200px;
  .footerBox {
    position: fixed;
    bottom: 0;
    left: 0;
    width: 100%;
    height: 170px;
    box-shadow: 0 0 2px 1px rgba(77, 77, 77, 0.2);
    z-index: 1;
    background: #fff;
  }
}
</style>
