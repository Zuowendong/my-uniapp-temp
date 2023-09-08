<template>
  <view class="sticky-list">
    <view class="tabsWrapper">
      <u-tabs
        :list="tabList"
        :current="currentIndex"
        @change="changeTab"
      ></u-tabs>
    </view>
    <view class="details">
      <view v-for="(item, index) in tabList" :key="index">
        <view :class="['detail-item', `detailItem${index}`]">
          <view class="title">{{ item.name }}</view>
          <view
            v-for="(info, idx) in item.infoList"
            :key="idx"
            class="infoItem"
          >
            <text class="label">{{ info.label }}：</text>
            <text class="value">{{ infoData[info.field] }}</text>
          </view>
        </view>
      </view>
    </view>
  </view>
</template>

<script>
export default {
  name: "InfoDetail",
  data() {
    const tabList = [
      {
        name: "基本信息",
        infoList: [
          { label: "楼盘信息", field: "base_name" },
          { label: "所在区域", field: "base_region" },
          { label: "楼盘地址", field: "base_address" },
        ],
      },
      {
        name: "住宅信息",
        infoList: [
          { label: "参考均价", field: "house_1" },
          { label: "参考建面", field: "house_2" },
          { label: "参考总价", field: "house_3" },
          { label: "开发商", field: "house_4" },
          { label: "装修情况", field: "house_5" },
          { label: "交房日期", field: "house_6" },
          { label: "产权年限", field: "house_7" },
          { label: "容积率", field: "house_8" },
          { label: "绿化率", field: "house_9" },
          { label: "物业公司", field: "house_10" },
          { label: "物业费", field: "house_11" },
          { label: "车位配比", field: "house_12" },
          { label: "车位个数", field: "house_13" },
        ],
      },
      {
        name: "车位信息",
        infoList: [
          { label: "参考建面", field: "car_1" },
          { label: "参考总价", field: "car_2" },
          { label: "车位个数", field: "car_3" },
        ],
      },
      {
        name: "商铺信息",
        infoList: [
          { label: "参考均价", field: "shop_1" },
          { label: "建筑面积", field: "shop_2" },
          { label: "参考总价", field: "shop_3" },
        ],
      },
      {
        name: "办公楼信息",
        infoList: [
          { label: "参考均价", field: "office_1" },
          { label: "建筑面积", field: "office_2" },
          { label: "参考总价", field: "office_3" },
        ],
      },
      {
        name: "许可证",
        infoList: [
          {
            label: "",
            field: "",
          },
        ],
      },
    ];
    return {
      tabList,
      infoData: {
        base_name: "东岸观邸-云尚丹霞",
        base_region: "上海市-浦东区-川沙",
        base_address:
          "上海市浦东新区川沙镇，东至丹霞路、西至浩韵路、南至D05B-03地块、北至新川东路",
        house_1: "约64000元/m²",
        house_2: "约84-155m²",
        house_3: "约498-664万/套",
        house_4: "上海国际旅游度假区川沙开发建设有限公司",
        house_5: "精装",
        house_6: "2024-12-31",
        house_7: "70年",
        house_8: "1.5",
        house_9: "35%",
        house_10: "金茂物业",
        house_11: "5.78元/m²/月",
        house_12: "超1:1",
        house_13: "768",
        car_1: "待定",
        car_2: "待定",
        car_3: "768",
        shop_1: "待定",
        shop_2: "待定",
        shop_3: "待定",
        office_1: "待定",
        office_2: "待定",
        office_3: "待定",
      },
      currentIndex: 0,
      distanceArr: [],
    };
  },
  onShow() {
    this.getDistanceArr();
  },

  onPageScroll(event) {
    const { scrollTop } = event;
    console.log("🔥🔥🔥🔥🔥🔥", scrollTop);
    if (scrollTop >= 80) {
      this.$nextTick(() => {
        const length = this.distanceArr.length;
        const index = this.distanceArr.findIndex(
          (el) => el - 80 - scrollTop > 0
        );
        this.currentIndex = index > 0 ? index - 1 : length - 1;
      });
    }
  },

  methods: {
    changeTab(tab) {
      this.currentIndex = tab.index;
    },
    getDistanceArr() {
      this.tabList.map((el, index) => {
        uni
          .createSelectorQuery()
          .select(`.detailItem${index}`)
          .boundingClientRect((data) => {
            this.distanceArr.push(data?.top);
          })
          .exec();
      });
    },
  },
};
</script>

<style lang="scss">
.sticky-list {
  position: relative;
  .tabsWrapper {
    position: fixed;
    top: 0;
    left: 0;
    background-color: #fff;
  }
  .details {
    padding-top: 80px;
    padding-bottom: 1000px;

    .detail-item {
      padding: 0 16px 40px 16px;
      .title {
        font-size: 20px;
        font-weight: bold;
        color: #000;
        padding-bottom: 10px;
      }
    }
  }

  .infoItem {
    font-size: 14px;
    display: flex;
    align-items: flex-start;
    padding: 5px 0;
    .label {
      flex-shrink: 0;
      width: 72px;
      color: #aaa;
      padding-right: 6px;
    }
    .value {
      flex: 1;
      color: #333;
    }
  }
}
</style>
