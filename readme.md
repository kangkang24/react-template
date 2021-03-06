###React version 16.0 版本脚手架
> 包含客户端，服务端渲染完整示例，使用了最新的react,并实现version 16 最新的服务端渲染;

```html
<!-- 分离的第三方依赖 -->
<script src="../dist/js/verdor.js"></script>

<!-- react -->
<script src="../dist/js/app.js"></script>
```
##### 安装命令和一些常用的npm脚本;
- yarn    (安装脚手架依赖)
- yarn preinstall    (检查node版本,最低6.0以上版本)
- yarn prestart    (删除dist 编译打包文件)
- yarn start (启动不包含服务端渲染的开发环境)
- yarn build (打包编译不包含服务端渲染的js,并启动)
- yarn prod (启动并打包服务端渲染)
- yarn lint (检查代码规范)
- yarn lint:watch (检查代码规范并监听)
- yarn test (启动单元测试)
- yarn test:watch (启动单元测试并监听)
- yarn remove-dist (删除dist文件夹)
- yarn clean-dist (清空dist文件夹)
##### 一些常见问题
1. 部署到服务器上,需要nginx 反向代理启动node.js 的http 服务;
2. 刷新之后 404 或者子路由报错；是使用了 BrowserRouter这个路由或者分割了代码。这个路由会开启h5 的history 模式;所以需要nginx的支持; nginx uri 定向到例如是打包文件是通过index.html 就重定向到index.html;如果是放在index.php就重定向到index.php就不会有这个问题了；
3. 服务端渲染的样式需要放在入口内。不是服务端渲染的就不用;
4. 这个脚手架是封装了axios 这个ajax库到redux中；所以不用在调用的地方引入axios;只需要在redux的action中使用我在redux中封装的axios 中间件的别名  例如: api.get api.post等就好了;action中也符合redux的方式;
5. 需要注意的是不是服务端渲染的启动命令也是不同的; 服务端渲染主要是为了解决seo问题，因为是单页应用。必须用户点击打开index.html 或index.php 或者站点后才能加载打包后的js 文件开始渲染节点内容; 没有加载js 也就不能渲染出节点。也就不能被搜索引擎检索到；  这也就是服务端渲染的需要;另外服务端渲染也加快网页加载速度; 只要服务器压力能承受住;
6. 为什么服务端渲染不分割代码。因为会报错；而且用了压缩代码会小很多;普通十多张页面不会超过1MB .1Mb对于服务端来说并没有什么..
##### 示例图片 || 第一张图片所标示的是服务端渲染错误提示; 这个可以不用管的。我试了对页面没什么影响
[![示例图片](./screen/1.jpg) "示例图片")](https://whevether.github.io/react-template-keep "示例图片")
##### 演示地址。不含服务端渲染;
[演示](https://whevether.github.io/react-template-keep "演示")