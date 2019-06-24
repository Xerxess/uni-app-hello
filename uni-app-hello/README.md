# 目录结构

* common ----------------------一些公开类
* compoents -------------------组件文件夹
* hybrid ---------------------- app内html
* pages ----------------------- page
* platforms ------------------- 整体目录条件编译 根据条件编译目录 将环境分开
  * app-plus  ---------------- h5-app
  * mp-weixin ---------------- weiwin
* static ---------------------- 静态资源 也可进行条件编译，微信的提交要求
  * app-plus  --------------- h5-app
  * mp-weixin ---------------- weiwin
* store ---------------------- vuex
* unpackage ------------------ 编译后的文件夹
* wxcompoents ---------------- 微信自定义组件
* App.vue -------------------- 应用配置，用来配置App全局样式以及监听
* main.js -------------------项目入口 可进行一些全局操作
* mainifest.json //////////// app 配置
* pages.json ///////////// 路由配制
* template.h5.html //////////省略
* uni.css ////////////////// 一些全局样式

# App.vue

* onLaunch 进行锁屏
* 加载全局样式
* onLaunch 检查更新状态
* plus.screen 屏幕管理api
* 监听app 初始化过程。
* 用户第一次进行应用需要在这里处理,
* 判断用户登录信息
* 重新登录检测
* 一些人脸识别

# main.js

* app 入口
* 加载配制
* 挂载全局对象、组件


# pages.json

* globalStyle 全局样式
* app-plus(app 兼容)
	* titleNView 设置原后导航条（按钮、搜索框、选择按钮、分享、背景色）
        * type 值为transparent时导航条透明渐变，高度则不被计算到内容上
	* bounce 是否回弹
	* pullToRefresh 下拉刷新 要配合uni.stopPullDownRefresh();才能关闭下拉刷新
* tabBar  配置项指定 tab 栏的表现
	* list tabBar每个项
		* iconPath  81px * 81px 不支持网络图片，不支持字体图标
		* selectedIconPath 选中时的图片路径
* subPackages 分包加载配置
	* [参考](https://uniapp.dcloud.io/collocation/pages?id=subpackages)