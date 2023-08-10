<template>
  <view> 关于页面 </view>
  <view @click="navTo"> 跳转到首页 </view>
</template>

<script setup>


const navTo = () => {
    uni.switchTab({
        url:'/pages/index/index?title=Az'
    })
}
</script>

<style lang="scss" scoped></style>
