<template>
  <view class="sticky-list">
    <view class="tabsWrapper">
      <u-tabs :list="list" :current="currentIndex" @change="changeTab"></u-tabs>
    </view>
    <view class="details">
      <view v-for="(item, index) in list" :key="index">
        <slot :name="`content${index}`"></slot>
      </view>
    </view>
  </view>
</template>

<script>
export default {
  name: "StickyList",
  props: {
    list: {
      type: Array,
      default: () => [],
    },
  },
  data() {
    return {
      currentIndex: 0,
    };
  },
  methods: {
    changeTab(tab) {
      this.currentIndex = tab.index;
    },
  },
};
</script>

<style lang="scss" scoped>
.tabsWrapper {
  padding-bottom: 36px;
}
.detail-item {
  padding: 0 16px 40px 16px;
  .title {
    font-size: 20px;
    font-weight: bold;
    color: #000;
    padding-bottom: 10px;
  }
}
</style>
