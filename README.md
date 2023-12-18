## page-spy-taro
该项目为在[Taro](taro-docs.jd.com)项目中使用[page-spy](https://www.pagespy.org)的问题展示的最小复现

### 项目（复现）说明
项目是根据 Taro 及 page-spy-web 官方文档创建的项目：由@tarojs/cli创建的Taro项目，然后根据 PageSpy 项目的说明在项目入口文件中接入 SDK
```html
  <!-- /src/index.html  -->
  <script crossorigin="anonymous" src="http://localhost:6752/page-spy/index.min.js"></script>
  <script>
    window.$pageSpy = new PageSpy();
  </script>
```
然后在页面上使用一个 `@tarojs/components` 的 `<Image />` 组件，填入一个不存在的图片路径(使图片请求报错)

### 运行项目
1. docker 安装 `page-spy`

```shell
docker run -d --restart=always -p 6752:6752 --name="pageSpy" ghcr.io/huolalatech/page-spy-web:release
```

2. 安装项目依赖
```shell
pnpm install
# or
npm install
```
3. 运行项目
```shell
pnpm dev:h5
# or
npm run dev:h5
```
