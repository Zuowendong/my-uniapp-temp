<template>
  <view class="activity-main">
    <view class="title">
      楼盘动态
      <text class="num">({{ stepsNum }}个)</text>
    </view>

    <view class="stepsWrapper">
      <u-steps :current="currentStep" direction="column" dot>
        <u-steps-item
          v-for="(item, index) in showOuterSteps"
          :key="index"
          :title="item.time"
        >
          <view slot="desc" class="stepItem" @click="handleViewStep(item)">
            {{ item.title }}
          </view>
        </u-steps-item>
      </u-steps>

      <view class="detialBtnBox">
        <view class="btn" @click="handleViewAll">全部动态</view>
      </view>
    </view>
  </view>
</template>

<script>
export default {
  data() {
    return {
      stepsList: [
        {
          time: "2023-09-10",
          title: "不止宜居·更川",
          content:
            "#不止宜居·更川# 沙沙浦东中部绿心 些铺就宜居底色一东岸观邸·约54公顷滨河大城 建面约83-155m精装高层&洋房",
          img: "",
        },
        {
          time: "2023-09-09",
          title: "一座大域定川沙",
          content:
            "#一座大城定川沙 内外美景，处处新趣生态大盘，自然共棠----东岸观邸建面约83-155阔景高层&精装洋",
          img: "",
        },
        {
          time: "2023-09-08",
          title: "2号线·公园里.生态美宅",
          content:
            "#2号线·公园里牛态美宅 高效通勤 漫享低密 装华宅 限量臻席一 东岸观邸 建面约83-96m精装高层 VIPLine: 021-5898 7777",
          img: "",
        },
        {
          time: "2023-09-02",
          title: "生态大盘，自然共赏",
          content:
            "#一座大城定川沙 内外美景，处处新趣生态大盘，自然共赏---- 东岸观邸建面约83-155m阔景高层&精装洋房",
          img: "",
        },
        {
          time: "2023-09-01",
          title: "2号线·公园里.生态美宅",
          content:
            "#2号线·公园里牛态美宅 高效通勤 漫享低密 装华宅 限量臻席一 东岸观邸 建面约83-96m精装高层 VIPLine: 021-5898 7777",
          img: "",
        },
        {
          time: "2023-08-31",
          title: "生态大盘，自然共赏",
          content:
            "#一座大城定川沙 内外美景，处处新趣生态大盘，自然共赏---- 东岸观邸建面约83-155m阔景高层&精装洋房",
          img: "",
        },
        {
          time: "2023-08-26",
          title: "2号线·公园里.生态美宅",
          content:
            "#2号线·公园里牛态美宅 高效通勤 漫享低密 装华宅 限量臻席一 东岸观邸 建面约83-96m精装高层 VIPLine: 021-5898 7777",
          img: "",
        },
        {
          time: "2023-08-25",
          title: "生态大盘，自然共赏",
          content:
            "#一座大城定川沙 内外美景，处处新趣生态大盘，自然共赏---- 东岸观邸建面约83-155m阔景高层&精装洋房",
          img: "",
        },
      ],
    };
  },
  computed: {
    stepsNum() {
      return this.stepsList ? this.stepsList.length : 0;
    },
    currentStep() {
      return this.stepsNum ? this.stepsNum - 1 : 0;
    },
    showOuterSteps() {
      let outerList = uni.$u.deepClone(this.stepsList);
      outerList.splice(5);
      return outerList;
    },
  },
  methods: {
    handleViewStep(raw) {
      uni.$u.route("pages/activity-list/detail", {});
    },
    handleViewAll() {
      uni.$u.route("pages/activity-list/list");
    },
  },
};
</script>

<style lang="scss">
.activity-main {
  background-color: #fff;
  padding: 20px;
  .title {
    height: 40px;
    line-height: 40px;
    font-size: 16px;
    font-weight: 600;
    position: relative;
    padding-left: 10px;
    margin-bottom: 10px;
    &::before {
      position: absolute;
      top: 50%;
      left: 0;
      transform: translatey(-50%);
      content: "";
      width: 2px;
      height: 18px;
      background-color: #4a6ddb;
    }
    .num {
      font-size: 14px;
      font-weight: normal;
      color: #ccc;
      padding-left: 4px;
    }
  }
  .stepsWrapper {
    position: relative;
    .stepItem {
      min-height: 50px;
      font-size: 13px;
      box-sizing: border-box;
      padding: 10px 0;
    }
    .detialBtnBox {
      width: 100%;
      position: absolute;
      left: 0;
      bottom: 0;
      padding-top: 100px;
      background: linear-gradient(
        rgba(255, 255, 255, 0.1),
        rgba(255, 255, 255, 0.8),
        rgba(255, 255, 255, 0.6),
        rgba(255, 255, 255, 1),
        #fff
      );
      z-index: 1;
      .btn {
        width: 100%;
        height: 45px;
        background-color: #ecf5ff;
        color: #2b85e4;
        border-radius: 8px;
        line-height: 45px;
        text-align: center;
      }
    }
  }
}
</style>
