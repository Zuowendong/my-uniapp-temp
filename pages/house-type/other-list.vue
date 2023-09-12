<template>
  <WrapperBox title="其他住宅户型" subtitle="(1)">
    <view class="houseWrapper">
      <u-tabs
        :list="typeList"
        :current="currentTab"
        lineColor="#fff"
        :activeStyle="{ color: '#2979ff' }"
        :inactiveStyle="{ color: '#606266' }"
        itemStyle="padding-left: 15px; padding-right: 15px; height: 34px;"
        @click="changeTab"
      >
      </u-tabs>

      <view class="houseList"> </view>
    </view>
  </WrapperBox>
</template>

<script>
import WrapperBox from "../../components/WrapperBox.vue";
export default {
  components: { WrapperBox },
  data() {
    return {
      typeList: [
        { name: "全部", key: 0 },
        { name: "三居", key: 3 },
        { name: "两居", key: 2 },
      ],
      currentTab: 0,
    };
  },
  methods: {
    changeTab(tab) {},
  },
};
</script>

<style lang="scss" scoped></style>
