<template>
  <view class="swiperWrapper">
    <u-swiper :list="swiperList" height="250" @click="handleViewImg"></u-swiper>
  </view>
</template>

<script>
export default {
  name: "",
  data() {
    return {
      swiperList: [
        {
          url: "https://raw.githubusercontent.com/Zuowendong/autocommit-robot/master/pictures/2023-8-29.png",
          title: "蒹葭苍苍，白露为霜。所谓伊人，在水一方",
        },
        {
          url: "https://raw.githubusercontent.com/Zuowendong/autocommit-robot/master/pictures/2023-8-30.png",
          title: "溯洄从之，道阻且长。溯游从之，宛在水中央",
        },
        {
          url: "https://raw.githubusercontent.com/Zuowendong/autocommit-robot/master/pictures/2023-8-31.png",
          title: "蒹葭萋萋，白露未晞。所谓伊人，在水之湄",
        },
      ],
    };
  },
  methods: {
    handleViewImg(index) {
      uni.$u.route("pages/swiper-list/detail", {
        idx: index,
      });
    },
  },
};
</script>

<style lang="scss">
.swiperWrapper {
  padding-top: 92px; // 44 + 48
}
</style>
