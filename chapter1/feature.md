# 产品主要特征
1. 跨更多平台，做到一套代码多端发行，不再需要对多个项目进行并行维护；

2. 运行体验好，组件、api与微信小程序相同；

3. 通用技术栈：vue语法、微信小程序api；

4. 开放生态组件更丰富：npm安装第三方包，支持微信小程序自定义组件和SDK等；

nativejs调用原生接口示例集合：https://ask.dcloud.net.cn/article/114

# 开发规范
## 一、 目录结构

| 文件夹名    | 内容    
| --------   | -----
| common     | 公用的资源,比如公共less/scss，公共方法util.js等
| components | uni-app组件目录，放可复用的组件     
| pages      | 业务页面文件存放的目录      
| static     | 存放应用引用静态资源（如图片、视频等）的地方，注意：静态资源只能存放于此    
| App.vue    | 应用配置，用来配置App全局样式以及监听应用生命周期
| main.js	   | Vue初始化入口文件
| mainfest.json | 配置应用名称、appid、logo、版本等打包信息。[详见](https://uniapp.dcloud.io/collocation/manifest)
| pages.json | 配置页面路由、导航条、选项卡等页面类信息。[详见](https://uniapp.dcloud.io/collocation/pages)

## 二、 代码结构
以pages里的vue文件为例，存在三个顶级语言模块。主要结构：
```
  <template> // 模板层
    <view class='content'>
     {{title}}
    </view>
  </template>
  <script> //脚本层
    export default {
      data() {
        return {
          title: '标题'
        }
	  }
    }
  </script>
  <style> //样式层
  </style>
```
- 模板层学习：[组件](https://uniapp.dcloud.io/component/README)与微信小程序组件保持一致。

- 脚本层学习：Vue,主要学习不支持的部分。[接口](https://uniapp.dcloud.io/api/README)与微信小程序接口保持一致。
- 样式层：注意单位upx,是相对基准宽度单位，uni-app规定屏幕基准宽度750upx。但是动态绑定的style不支持用upx。

支持import导入组件文件及样式文件

## 三、 开发规范
### 1. 页面文件遵循 Vue 单文件组件 (SFC) 规范
- .vue 文件是一个自定义的文件类型，用类 HTML 语法描述一个 Vue 组件。每个 .vue 文件包含三种类型的顶级语言块 ```<template>、<script> 和 <style>```
- 每个 .vue 文件最多包含一个 ```<template>``` 块

### 2. 组件标签靠近小程序规范
&emsp;&emsp;后文单独记录


### 3. 组件标签靠近小程序规范
&emsp;&emsp;接口能力（JS API）靠近微信小程序规范，但需将前缀 wx 替换为 uni。后文单独记录

### 4. 数据绑定及事件处理同 Vue.js 规范，同时补充了App及页面的生命周期
&emsp;&emsp;详见生命周期


### 5. 建议使用flex布局进行开发