<template>
  <WrapperBox title="户型介绍" subtitle="(2)">
    <view class="houseWrapper">
      <u-tabs
        :list="typeList"
        :current="currentTab"
        lineColor="#fff"
        :activeStyle="{ color: '#2979ff', fontWeight: 'bold' }"
        :inactiveStyle="{ color: '#606266' }"
        itemStyle="padding-left: 15px; padding-right: 15px; height: 34px;"
        @click="changeTab"
      >
      </u-tabs>

      <view class="typeList">
        <u-scroll-list>
          <view
            v-for="(item, index) in houseList"
            :key="index"
            class="typeItem"
            @click="handleViewDetail(item)"
          >
            <view class="imgBox">
              <u--image
                :src="item.img"
                width="132px"
                height="120px"
                mode="heightFix"
              ></u--image>
            </view>
            <view class="name">{{ item.name }}</view>
            <view class="desc">{{ item.desc }}</view>
            <view class="price">{{ item.price }}</view>
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
      typeList: [
        { name: "全部", key: 0 },
        { name: "三居", key: 3 },
        { name: "两居", key: 2 },
      ],
      list: [
        {
          key: 3,
          name: "三室一厅一卫",
          desc: "建面94.47m²，朝向朝南",
          price: "待定",
          img: require("../../static/images/houseType.png"),
        },
        {
          key: 3,
          name: "三室两厅一卫",
          desc: "建面101.16m²，南北通透",
          price: "待定",
          img: require("../../static/images/houseType.png"),
        },
        {
          key: 3,
          name: "三室两厅两卫",
          desc: "建面113.24m²，南北通透",
          price: "待定",
          img: require("../../static/images/houseType.png"),
        },
        {
          key: 2,
          name: "两室两厅两卫",
          desc: "建面102.41m²，两室朝南",
          price: "待定",
          img: require("../../static/images/houseType.png"),
        },
        {
          key: 2,
          name: "两室两厅一卫",
          desc: "建面96.72m²，朝向朝南",
          price: "待定",
          img: require("../../static/images/houseType.png"),
        },
        {
          key: 2,
          name: "两室一厅一卫",
          desc: "建面87.67m²，朝向朝南",
          price: "待定",
          img: require("../../static/images/houseType.png"),
        },
      ],
      houseList: [],
      currentTab: 0,
    };
  },
  watch: {
    currentTab: {
      handler(val) {
        if (val == 0) {
          this.houseList = this.list;
        }
      },
      immediate: true,
    },
  },
  methods: {
    changeTab(tab) {
      this.currentKey = tab.index;
      if (tab.key == 0) {
        this.houseList = this.list;
      } else {
        this.houseList = this.list.filter((item) => item.key == tab.key);
      }
    },

    handleViewDetail(raw) {
      uni.$u.route("pages/house-type/detail", {});
    },
  },
};
</script>

<style lang="scss" scoped>
.houseWrapper {
  .typeList {
    .typeItem {
      margin-right: 10px;
      .imgBox {
        width: 222px;
        height: 168px;
        border: 1px dashed #ccc;
        box-sizing: border-box;
        padding: 20px;
        display: flex;
        align-items: center;
        justify-content: center;
        margin-bottom: 20px;
      }
      .name {
        font-size: 15px;
        font-weight: bold;
      }
      .desc {
        font-size: 13px;
        color: #666;
        padding: 10px 0;
      }
      .price {
        font-size: 15px;
        color: #dd6161;
      }
    }
  }
}
</style>
