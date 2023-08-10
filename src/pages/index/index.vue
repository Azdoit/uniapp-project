<template>
  <view class="content">
    <image class="logo" src="/static/logo.png" />
    <view class="text-area">
      <text class="title">{{ title }}</text>
      <view>从关于页面传过来的参数：{{ prop }}</view>
      <navigator
        url="/pages/about/index"
        open-type="navigate"
        hover-class="navigator-hover"
      >
        跳转到关于页面
      </navigator>
    </view>
  </view>
</template>

<script setup lang="ts">
import { onLoad } from "@dcloudio/uni-app";
import { ref } from "vue";
const title = ref("Hello");
const prop = ref("");
onLoad((option) => {
  prop.value = option?.title;
  uni.request({
    url: "https://api-v2.xdclass.net/api/card/v1/list", //仅为示例，并非真实接口地址。
    success: function (res) {
      console.log(res.data.data);
    },
  });
});
</script>

<style>
.content {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
}

.logo {
  height: 200rpx;
  width: 200rpx;
  margin-top: 200rpx;
  margin-left: auto;
  margin-right: auto;
  margin-bottom: 50rpx;
}

.text-area {
  display: flex;
  flex-direction: column;
  justify-content: center;
}

.title {
  font-size: 36rpx;
  color: #8f8f94;
}
</style>
