<template>
  <view class="counselorWrapper">
    <u-row gutter="14" customStyle="margin-bottom: 30px">
      <u-col span="2">
        <u-avatar :src="src"></u-avatar>
      </u-col>
      <u-col span="10">
        <view class="nameWrapper">
          <text>任淑丽</text>
          <text class="address">东岸观邸-云尚丹霞</text>
        </view>
        <view class="region">浦东新区·川沙 | 均价64000元/m²</view>
      </u-col>
    </u-row>
    <u-row gutter="24">
      <u-col span="6">
        <view class="button btn1">加我微信</view>
      </u-col>
      <u-col span="6">
        <view class="button btn2">电话咨询</view>
      </u-col>
    </u-row>
  </view>
</template>

<script>
export default {
  name: "FooterBox",
  data() {
    return {
      src: "http://pic2.sc.chinaz.com/Files/pic/pic9/202002/hpic2119_s.jpg",
    };
  },
  methods: {},
};
</script>

<style lang="scss">
.counselorWrapper {
  padding: 10px 14px 40px 14px;
  box-sizing: border-box;

  .nameWrapper {
    .address {
      font-size: 14px;
      margin-left: 10px;
      background-color: #fcbd71;
      padding: 2px 4px;
      border-radius: 20px;
      color: #333;
    }
  }
  .region {
    padding-top: 10px;
    color: #ccc;
    font-size: 13px;
  }

  .button {
    width: 100%;
    height: 34px;
    border: 1px solid #2979ff;
    border-radius: 6px;
    line-height: 34px;
    text-align: center;
  }
  .btn1 {
    color: #2979ff;
  }
  .btn2 {
    background-color: #2979ff;
    color: #fff;
  }
}
</style>
