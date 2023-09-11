<template>
  <view class="activeListBox">
    <u-steps :current="currentStep" direction="column" dot>
      <u-steps-item
        v-for="(item, index) in list"
        :key="index"
        :title="item.time"
      >
        <view slot="desc" class="stepItem" @click="handleViewStep(item)">
          <view class="textBox">
            <view class="title">{{ item.title }}</view>
            <view class="content">{{ item.content }}</view>
          </view>
          <u--image
            :src="item.img"
            width="120px"
            height="90px"
            mode="center"
            radius="6"
          ></u--image>
        </view>
      </u-steps-item>
    </u-steps>
  </view>
</template>

<script>
export default {
  data() {
    return {
      list: [
        {
          time: "2023-09-10",
          title: "不止宜居·更川",
          content:
            "#不止宜居·更川# 沙沙浦东中部绿心 些铺就宜居底色一东岸观邸·约54公顷滨河大城 建面约83-155m精装高层&洋房",
          img: "https://raw.githubusercontent.com/Zuowendong/autocommit-robot/master/pictures/2023-8-29.png",
        },
        {
          time: "2023-09-09",
          title: "一座大域定川沙",
          content:
            "#一座大城定川沙 内外美景，处处新趣生态大盘，自然共棠----东岸观邸建面约83-155阔景高层&精装洋",
          img: "https://raw.githubusercontent.com/Zuowendong/autocommit-robot/master/pictures/2023-8-29.png",
        },
        {
          time: "2023-09-08",
          title: "2号线·公园里.生态美宅",
          content:
            "#2号线·公园里牛态美宅 高效通勤 漫享低密 装华宅 限量臻席一 东岸观邸 建面约83-96m精装高层 VIPLine: 021-5898 7777",
          img: "https://raw.githubusercontent.com/Zuowendong/autocommit-robot/master/pictures/2023-8-29.png",
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
    currentStep() {
      return this.list.length ? this.list.length - 1 : 0;
    },
  },
  methods: {
    handleViewStep(raw) {
      uni.$u.route("pages/activity-list/detail", {});
    },
  },
};
</script>

<style lang="scss">
.activeListBox {
  padding: 0 20px 0 15px;
  .stepItem {
    display: flex;
    align-items: center;
    padding: 16px 0 20px 0;
    .textBox {
      flex: 1;
      padding-right: 10px;
      .title {
        font-size: 16px;
        color: #333;
        margin-bottom: 10px;
      }
      .content {
        font-size: 14px;
        color: #666;
      }
    }
  }
}
</style>
