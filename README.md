<!--
 * @Author: wangqiang
 * @Date: 2020-03-26 11:57:29
 * @LastEditors: wangqiang
 * @LastEditTime: 2020-03-26 17:12:17
 * @FilePath: \tengxunyun\watermark-component\README.md
 * @Descripttion: 
 -->
# watermark-component
`watermark-com`git remote add origin git@github.com:wangqiangstar/watermark-component.git。

## 一、使用方法

### 1、本地引入js文件

第一步：在页面中引入水印文件
```
<script type="text/javascript" src=""></script>
```

第二步：在确保页面DOM加载完毕之后，调用watermark方法
```
watermarkObj.watermark({ text: "这是测试水印" })
```

### 2、npm包引入

第一步：npm获取水印包
```
npm install watermark-component --save
# yarn add watermark-component
```

第二步：引入水印模块 
```
import { watermark } from 'watermark-com'
// const watermark = require('watermark-com')
```

第三步：在确保页面DOM加载完毕之后，调用watermark方法
```
watermark({ text: "这是测试水印" })
```

注意：当需要加水印的内容部分有滚动的情况，我们建议在需要加载水印的容器下加一个：
```
<div id='watermarkId'>content</div>
```
把需要加水印的内容部分包裹起来，以这个div当做水印元素的父节点，content为需要加水印的内容节点

## 二、配置项

```
{
  id: 'wm_div_id', // 水印总体的id
  text: '测试水印', // 水印的内容
  transparency: 0.15, // 水印透明度
  fontSize: 16, // 水印字体大小，以px为单位
  parentLeft: 0, // 水印整体左边距离
  parentTop: 0, // 水印整体顶边距离
  parentRight: 0, // 水印整体右边距离
  parentBottom: 0, // 水印整体顶边距离
  singleWidth: 200, // 单个水印宽度
  singleHeight: 200, // 单个水印长度
  slope: -15, // 水印倾斜度数
  parentSelector: null, // 水印插件挂载的父元素选取器,不输入则默认挂在body上
}
```

注意：
+ 若watermark()没有传任何配置则使用的是以上的默认配置，常用的配置项是text，若对水印的样式有要求的可自行传入相关的配置项。
+ parentSelector不传则默认挂在body上。
+ 若挂载在body下，水印不会随着内容的滚动而滚动，若挂载到滚动的内容上则可以随着内容的滚动而滚动，可根据需求自行选择。
+ 加水印后有可能会影响到内容的绝对定位，若有影响需调整页面样式。

## 三、浏览器支持情况

  Chrome、FireFox、Safari、IE10及以上浏览器支持全部功能

  IE10及以下不支持水印被用户手动调用开发者工具删除水印dom的情况 