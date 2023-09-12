<template>
  <view class="typeDetail">
    <view class="imgWrapper">
      <u--image :src="houseInfo.img" width="100%" mode="aspectFit"></u--image>
    </view>
    <WrapperBox>
      <view class="title">3室2厅2卫(高层住宅)</view>
      <view class="price">
        参考单价：
        <text class="num">待定</text>
      </view>
      <view class="tagList">
        <view
          v-for="(tag, tagIndex) in tagList"
          :key="tagIndex"
          class="tagItem"
        >
          <u-tag v-if="tag.primary" :text="tag.name" size="mini"></u-tag>
          <u-tag
            v-else
            :text="tag.name"
            size="mini"
            plain
            bgColor="#eee"
            color="#333"
            borderColor="#eee"
          >
          </u-tag>
        </view>
      </view>
      <view class="infoText">
        <u-row customStyle="margin-bottom: 6px">
          <u-col span="5"> <view class="text">83.45m²</view> </u-col>
          <u-col span="4"> <view class="text">待定</view> </u-col>
          <u-col span="3"> <view class="text">朝南</view> </u-col>
        </u-row>
        <u-row>
          <u-col span="5"> <view class="subText">参考建面</view> </u-col>
          <u-col span="4"> <view class="subText">参考总价</view> </u-col>
          <u-col span="3"> <view class="subText">朝向</view> </u-col>
        </u-row>
      </view>
    </WrapperBox>
    <WrapperBox title="户型点评">
      <text class="comment">
        南北通透，标准飞机户型，功能齐全，三开间朝南，采光充足，二房面积一房的使用率拓宽功能;
      </text>
    </WrapperBox>
    <WrapperBox title="其他住宅户型">
      <text class="comment">
        南北通透，标准飞机户型，功能齐全，三开间朝南，采光充足，二房面积一房的使用率拓宽功能;
      </text>
    </WrapperBox>
  </view>
</template>

<script>
import WrapperBox from "../../components/WrapperBox.vue";
export default {
  components: { WrapperBox },
  data() {
    return {
      houseInfo: {
        name: "三室一厅一卫",
        desc: "建面94.47m²，朝向朝南",
        price: "待定",
        img: require("../../static/images/houseType.png"),
      },
      tagList: [
        { name: "在售", primary: true },
        { name: "小户型" },
        { name: "户型方正" },
        { name: "卧室朝南" },
      ],
    };
  },
  methods: {},
};
</script>

<style lang="scss" scoped>
.typeDetail {
  background-color: #f6f6f8;
  .imgWrapper {
    background-color: #fff;
    padding: 0 20px;
  }
  .title {
    font-size: 20px;
    font-weight: 600;
  }
  .price {
    font-size: 14px;
    color: #aaa;
    padding: 14px 0 12px 0;
    .num {
      font-size: 16px;
      color: #fa3534;
    }
  }
  .tagList {
    display: flex;
    align-items: center;
    .tagItem {
      margin-right: 5px;
    }
  }

  .infoText {
    padding-top: 30px;
    padding-bottom: 15px;
    .text {
      display: flex;
      align-items: center;
    }
    .subText {
      font-size: 14px;
      color: #aaa;
    }
    .prefixUnit {
      margin-right: 2px;
    }
  }
  .comment {
    font-size: 14px;
    color: #666;
  }
}
</style>
