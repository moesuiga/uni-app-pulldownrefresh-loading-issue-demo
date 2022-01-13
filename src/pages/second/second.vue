<template>
  <view>第二页</view>
</template>

<script>
export default {
  onPullDownRefresh() {
    console.debug('下拉刷新2');
    uni.stopPullDownRefresh();
  }
}
</script>

<style>

</style>
