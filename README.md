# uni-app+vue3 下拉刷新问题的示例

本示例结构通过 uni-app 官方文档提示，使用Vue3/Vite版命令创建
```shell
npx degit dcloudio/uni-preset-vue#vite my-vue3-project
```

## 使用方式

下载项目到本地
```shell
yarn         // npm install
yarn dev:h5  // npm run dev:h5
```

## 问题描述：

假定现在有两个页面：页面一、页面二，且这两个页面都开启了下拉刷新，即在 `pages.json` 文件中配置了 `"enablePullDownRefresh": true`。
同时页面内也存在以下代码：
```js
export default {
  // ...
  onPullDownRefresh() {
    // ...
    uni.stopPullDownRefresh();
  },
  // ...
}
```
单独打开页面一、页面二，测试下拉刷新，无异常。
但是：**从页面一跳转至页面二后，再返回页面一，页面一下拉刷新后，loading不再消失，并在后续无法下拉刷新**。
