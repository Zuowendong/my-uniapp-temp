<template>
  <view>
    <HeaderTitle />
    <view class="headerText">
      <u-row customStyle="margin-bottom: 6px">
        <u-col span="6">
          <view class="text">待定</view>
        </u-col>
        <u-col span="6">
          <view class="text">
            <text>待定</text>
          </view>
        </u-col>
      </u-row>
      <u-row>
        <u-col span="6"> <view class="subText">参考总价</view> </u-col>
        <u-col span="6"> <view class="subText">参考建面</view> </u-col>
      </u-row>
    </view>
    <view class="infoBox">
      <u-row customStyle="margin-bottom: 10px">
        <u-col span="12">
          <view class="alone">
            <text class="subText">参考均价:</text>
            <text class="labelText">待定</text>
          </view>
        </u-col>
      </u-row>
      <u-row customStyle="margin-bottom: 10px">
        <u-col span="12">
          <view class="alone">
            <text class="subText">许可证:</text>
            <u-icon name="photo"></u-icon>
            <text>浦东新区房管(2023)预字0000212号</text>
          </view>
        </u-col>
      </u-row>
      <u-row customStyle="margin-bottom: 24px">
        <u-col span="12">
          <view class="alone">
            <text class="subText">地址:</text>
            <text class="address">
              浦东新区-川沙上海市浦东新区川沙镇，东至丹霞路、西至浩韵路、南至D05B-03地块、北至新川东路
            </text>
            <u-icon name="map"></u-icon>
          </view>
        </u-col>
      </u-row>
      <view class="aloneBtn" @click="handleViewDetails">查看楼盘完整信息</view>
    </view>
  </view>
</template>

<script>
import HeaderTitle from "./components/header-title.vue";
export default {
  name: "InfoShop",
  components: { HeaderTitle },
  data() {
    return {};
  },
  methods: {
    handleViewDetails() {
      uni.$u.route("pages/switch-msg/info-detail", {
        tabIndex: 3,
      });
    },
  },
};
</script>

<style lang="scss">
@import "./info.scss";
</style>
