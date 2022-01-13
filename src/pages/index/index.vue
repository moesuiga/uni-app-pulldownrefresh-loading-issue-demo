<template>
  <view style="padding: 12px;">
    <view>这是首页</view>
    <view>
      本页开启了下拉刷新，并在 onPullDownRefresh 回调内调用了 uni.stopPullDownRefresh 以关闭loading。
    </view>
    <view>本页测试下拉刷新没有问题。</view>
    <view>但在点击下面按钮跳转至另一个开启了下拉刷新的页面后，再返回本页，下拉刷新后，loading 不会消失。</view>
    <button @click="nav">跳转至另一个开启了下拉刷新的页面</button>
  </view>
</template>

<script>
export default {
  onPullDownRefresh() {
    console.debug('下拉刷新');
    uni.stopPullDownRefresh();
  },
  methods: {
    nav() {
      uni.navigateTo({ url: '/pages/second/second' });
    }
  }
}
</script>

<style>

</style>
