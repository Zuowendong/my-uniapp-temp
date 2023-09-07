<template>
  <view>
    <u-row>
      <u-col
        v-for="(item, index) in list"
        :key="index"
        span="3"
        @click="changeTab(index)"
      >
        <view :class="['tabItem', currentTab === index ? 'activeTab' : '']">
          <text>{{ item.name }}</text>
        </view>
      </u-col>
    </u-row>
  </view>
</template>

<script>
export default {
  name: "TabList",
  data() {
    return {
      list: [
        { name: "住宅" },
        { name: "车位" },
        { name: "商铺" },
        { name: "办公楼" },
      ],
      currentTab: 0,
    };
  },
  methods: {
    changeTab(index) {
      this.currentTab = index;
    },
  },
};
</script>

<style lang="scss">
.tabItem {
  width: 100%;
  height: 72px;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  border-bottom: 2px solid transparent;
}
.activeTab {
  background-color: #ecf5ff;
  color: #2b85e4;
  border-color: #2b85e4;
}
</style>
