<template>
  <view>
    <HeaderTitle />

    <view class="headerText">
      <u-row customStyle="margin-bottom: 6px">
        <u-col span="3">
          <view class="text">3室</view>
        </u-col>
        <u-col span="5">
          <view class="text">
            <text class="subText prefixUnit">约</text>
            <text>498-664万/套</text>
          </view>
        </u-col>
        <u-col span="4">
          <view class="text">
            <text class="subText prefixUnit">约</text>
            <text>84-155m²</text>
          </view>
        </u-col>
      </u-row>
      <u-row>
        <u-col span="3"> <view class="subText">参考户型</view> </u-col>
        <u-col span="5"> <view class="subText">参考总价</view> </u-col>
        <u-col span="4"> <view class="subText">参考建面</view> </u-col>
      </u-row>
    </view>

    <view class="infoBox">
      <u-row customStyle="margin-bottom: 10px">
        <u-col span="12">
          <view class="alone">
            <text class="subText">参考均价:</text>
            <text class="labelText">约64000元/m²</text>
          </view>
        </u-col>
      </u-row>
      <u-row customStyle="margin-bottom: 10px">
        <u-col span="6">
          <view class="groupLeft">
            <text class="subText">绿化率:</text>
            <text>35%</text>
          </view>
        </u-col>
        <u-col span="6">
          <view class="groupRight">
            <text class="subText">容积率:</text>
            <text>1.5</text>
          </view>
        </u-col>
      </u-row>
      <u-row customStyle="margin-bottom: 10px">
        <u-col span="6">
          <view class="groupLeft">
            <text class="subText">物业费:</text>
            <text>5.78元/m²/月</text>
          </view>
        </u-col>
        <u-col span="6">
          <view class="groupRight">
            <text class="subText">车位比:</text>
            <text>超1:1</text>
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
  name: "InfoHouse",
  components: { HeaderTitle },
  data() {
    return {};
  },
  methods: {
    handleViewDetails() {
      uni.$u.route("pages/switch-msg/info-detail", {
        idx: 1,
      });
    },
  },
};
</script>

<style lang="scss">
@import "./info.scss";
</style>
