<template>
  <view class="album-main">
    <view class="header">东岸观邸-云尚丹霞</view>
    <view class="content">
      双国企联袂打造首个稀缺低密环水社区;板块C位，54万方待开发体量，大城气势呼之欲出，紧邻黄金二号线，享便捷公共交通出行生活，浦东稀缺地铁房:全龄社区，产品多样，释放你的选择面，84-150m三房四房，目前项目正在热销中，无需积分，不限售
    </view>

    <view class="album-container">
      <view class="album-list">
        <u-row gutter="6">
          <u-col span="4">
            <u--image
              src="https://cdn.uviewui.com/uview/album/1.jpg"
              width="110px"
              height="110px"
              mode="aspectFill"
              radius="6"
            ></u--image>
          </u-col>
          <u-col span="4">
            <u--image
              src="https://cdn.uviewui.com/uview/album/1.jpg"
              width="110px"
              height="110px"
              mode="aspectFill"
              radius="6"
            ></u--image>
          </u-col>
          <u-col span="4">
            <u--image
              src="https://cdn.uviewui.com/uview/album/1.jpg"
              width="110px"
              height="110px"
              mode="aspectFill"
              radius="6"
            ></u--image>
          </u-col>
        </u-row>
      </view>
      <view class="showDetails" @click="handleViewAlbum">
        <u-icon name="arrow-right"></u-icon>
      </view>
    </view>
  </view>
</template>

<script>
export default {
  data() {
    return {};
  },
  methods: {
    handleViewAlbum() {
      uni.$u.route("pages/swiper-list/detail", {});
    },
  },
};
</script>

<style lang="scss">
.album-main {
  background-color: #fff;
  padding: 25px 15px 6px 15px;
  color: #3c5298;
  margin-bottom: 10px;
  .header {
    font-size: 20px;
    font-weight: 500;
  }
  .content {
    padding-top: 20px;
    font-size: 14px;
    padding-bottom: 35px;
  }
  .album-container {
    height: 110px;
    display: flex;
    align-items: center;
    .album-list {
      flex: 1;
    }
    .showDetails {
      width: 20px;
      height: 100%;
      display: flex;
      align-items: center;
      justify-content: center;
      background-color: #eee;
      border-radius: 4px;
      margin-left: 6px;
    }
  }
}
</style>
