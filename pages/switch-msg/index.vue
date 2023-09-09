<template>
  <view class="switchWrapper">
    <TabList :list="tabList" v-model="currentTab" defaultTabKey="house" />
    <view class="infoWrapper">
      <InfoHouse v-show="currentTab === 'house'" />
      <InfoCar v-show="currentTab === 'car'" />
      <InfoShop v-show="currentTab === 'shop'" />
      <InfoOffice v-show="currentTab === 'office'" />
    </view>
  </view>
</template>

<script>
import TabList from "./components/TabList.vue";
import InfoHouse from "./info-house.vue";
import InfoCar from "./info-car.vue";
import InfoShop from "./info-shop.vue";
import InfoOffice from "./info-office.vue";
export default {
  name: "SwitchMsg",
  components: { TabList, InfoHouse, InfoCar, InfoShop, InfoOffice },
  data() {
    return {
      tabList: [
        { name: "住宅", key: "house" },
        { name: "车位", key: "car" },
        { name: "商铺", key: "shop" },
        { name: "办公楼", key: "office" },
      ],
      currentTab: "house",
    };
  },
  methods: {},
};
</script>

<style lang="scss">
.switchWrapper {
  background-color: #f6f6f8;
  margin-bottom: 10px;
  .infoWrapper {
    margin-top: 10px;
    background-color: #fff;
    padding: 20px;
    padding-bottom: 0;
  }
}
</style>
