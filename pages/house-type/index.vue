<template>
  <WrapperBox title="户型介绍" subtitle="(2)">
    <view class="houseWrapper">
      <u-tabs
        :list="typeList"
        lineColor="#fff"
        :activeStyle="{ color: '#2979ff', fontWeight: 'bold' }"
        :inactiveStyle="{ color: '#606266' }"
        itemStyle="padding-left: 15px; padding-right: 15px; height: 34px;"
      >
      </u-tabs>

      <view>
        <u-scroll-list>
          <view v-for="(item, index) in list" :key="index">
            <view class="">{{ item.name }}</view>
          </view>
        </u-scroll-list>
      </view>
    </view>
  </WrapperBox>
</template>

<script>
import WrapperBox from "../../components/WrapperBox";
export default {
  components: { WrapperBox },
  data() {
    return {
      typeList: [{ name: "全部" }, { name: "三居" }, { name: "两居" }],
      list: [
        {
          key: 3,
          name: "三室一厅一卫",
        },
        {
          key: 3,
          name: "三室两厅一卫",
        },
        {
          key: 3,
          name: "三室两厅两卫",
        },
        {
          key: 2,
          name: "两室两厅两卫",
        },
        {
          key: 2,
          name: "两室两厅一卫",
        },
        {
          key: 3,
          name: "两室一厅一卫",
        },
      ],
    };
  },
  methods: {},
};
</script>

<style lang="less" scoped></style>
