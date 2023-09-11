<template>
  <view class="swiperDetail">
    <u-tabs :list="tabList" @click="chooseTab"></u-tabs>
    <view class="swiperWrapper">
      <view class="swiperBox">
        <u-swiper
          :list="imgList"
          @change="(e) => (currentNum = e.current)"
          :autoplay="false"
          indicatorStyle="right: 20px"
          height="250"
        >
          <view slot="indicator" class="indicator-num">
            <text class="indicator-num__text">
              {{ currentNum + 1 }}/{{ imgList.length || 1 }}
            </text>
          </view>
        </u-swiper>
      </view>
    </view>
  </view>
</template>

<script>
export default {
  data() {
    return {
      tabList: [
        {
          name: "装修效果图",
          imgs: [
            {
              url: "https://raw.githubusercontent.com/Zuowendong/autocommit-robot/master/pictures/2023-8-29.png",
            },
            {
              url: "https://raw.githubusercontent.com/Zuowendong/autocommit-robot/master/pictures/2023-8-30.png",
            },
            {
              url: "https://raw.githubusercontent.com/Zuowendong/autocommit-robot/master/pictures/2023-8-31.png",
            },
          ],
        },
        {
          name: "样板间效果图",
          imgs: [],
        },
        {
          name: "环境规划图",
          imgs: [],
        },
        {
          name: "配套实景图",
          imgs: [],
        },
        {
          name: "楼盘实景图",
          imgs: [],
        },
      ],
      imgList: [],
      currentNum: 0,
    };
  },
  onLoad(options) {
    const { idx } = options;
    this.imgList = this.tabList[idx || 0].imgs;
  },
  methods: {
    chooseTab(tab) {
      this.currentNum = 0;
      this.imgList = tab.imgs;
    },
  },
};
</script>

<style lang="scss">
.swiperDetail {
  height: 100vh;
  display: flex;
  flex-direction: column;
}
.swiperWrapper {
  flex: 1;
  background-color: #000;
  height: 100%;
  display: flex;
  align-items: center;
  justify-content: center;
  .swiperBox {
    width: 100%;
    height: 300px;
  }
}

.indicator-num {
  padding: 2px 0;
  background-color: rgba(0, 0, 0, 0.35);
  border-radius: 100px;
  width: 35px;
  @include flex;
  justify-content: center;

  &__text {
    color: #ffffff;
    font-size: 12px;
  }
}
</style>
