<template>
  <WrapperBox title="位置及周边配套">
    <view class="mapBox">
      <map
        style="width: 100%; height: 200px"
        :latitude="latitude"
        :longitude="longitude"
      >
      </map>
    </view>
    <view class="tabBox">
      <u-tabs :list="tabList" @click="changeTab"></u-tabs>
    </view>
  </WrapperBox>
</template>

<script>
import WrapperBox from "../../components/WrapperBox.vue";
export default {
  components: { WrapperBox },
  data() {
    return {
      latitude: 39.909,
      longitude: 116.39742,
      tabList: [
        { name: "地铁(2)" },
        { name: "公交(6)" },
        { name: "教育(3)" },
        { name: "医院(2)" },
        { name: "银行(8)" },
        { name: "购物(4)" },
      ],
    };
  },
  methods: {
    changeTab(tab) {
      console.log("🔥🔥🔥🔥🔥🔥", tab);
    },
  },
};
</script>

<style lang="scss" scoped>
.mapBox {
  margin-bottom: 20px;
}
</style>
