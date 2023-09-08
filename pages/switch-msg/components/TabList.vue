<template>
  <view>
    <u-row>
      <u-col
        v-for="item in list"
        :key="item.key"
        span="3"
        @click="changeTab(item.key)"
      >
        <view :class="['tabItem', currentTab === item.key ? 'activeTab' : '']">
          <text>{{ item.name }}</text>
        </view>
      </u-col>
    </u-row>
  </view>
</template>

<script>
export default {
  name: "TabList",
  props: {
    list: {
      type: Array,
      default: () => [],
    },
    value: {
      type: String,
      default: "",
    },
    defaultTabKey: {
      type: String,
      default: "",
    },
  },
  model: {
    prop: "value",
    event: "input",
  },
  data() {
    return {
      currentTab: "",
    };
  },
  watch: {
    defaultTabKey: {
      handler(val) {
        this.currentTab = val;
      },
      immediate: true,
    },
  },
  methods: {
    changeTab(key) {
      this.currentTab = key;
      this.$emit("input", key);
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
  background-color: #fff;
}
.activeTab {
  background-color: #ecf5ff;
  color: #2b85e4;
  border-color: #2b85e4;
}
</style>
