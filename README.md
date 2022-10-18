# MumuDroidBrowser 脚本浏览器
## GooglePlay下载地址：
https://play.google.com/store/apps/details?id=cn.geekapp.ggstudioweb

## 国内镜像下载：
https://www.mumudroid.com/detail/107.html


## 已兼容油猴Tampermonkey语法：
1.  @name
2.  @version
3.  @author
4.  @description
5.  @include
6.  @match
7.  @exclude
8.  @require
9.  @run-at

## 已兼容油猴Tampermonkey函数：
1.  GM_setValue(name, value)
2.  GM_getValue(name, defaultValue)
3.  GM_deleteValue(name)
4.  GM_log(message)

## 原生接口支持
#### 1.显示信息接口名称：toast(msg)

使用示例：geekapp.toast('toast的信息内容');

#### 2.复制到粘贴板接口名称：copy(text)

使用示例：geekapp.copy('复制的文本内容');

#### 3.日志接口名称：log(text)

使用示例：console.log('日志内容');

说明：在右上角菜单中点击[控制台]可以显示日志面板，您也可以直接使用console.error(message)。

#### 4.模拟点击接口名称：click(x, y)

使用示例1：geekapp.click(100, 200); //在网页右上角为原点的坐标(100,200)的位置触发一次点击事件。

使用示例2：geekapp.click(0.5, 0.5); //在网页中心点触发一次点击事件。

说明：传入0-1的参数时(推荐)，默认以屏幕比例处理。>=1时以像素位置处理。

#### 5.模拟滑动接口名称：swipe(x1, y1, x2, y2)

使用示例1：geekapp.swipe(100, 200, 100, 400); //从坐标(100,200)开始滑动到坐标(100,400)及模拟向下滑动，滑动距离为400-200=200像素。

使用示例2：geekapp.swipe(0.5, 0.8, 0.5, 0.2); //从坐标(0.5,0.8)开始滑动到坐标(0.5,0.2)及模拟向上滑动。滑动距离为0.8-0.2=0.6及网页高度的60%的距离。

说明：传入0-1的参数时(推荐)，默认以屏幕比例处理。>=1时以像素位置处理。

#### 6.网页截图接口名称：getImage(left, top, width, height, quality)

使用示例1：var base64data = geekapp.getImage(0, 0, 100, 100, 75); //获取网页左上角100X100矩形区域且质量为75的base64图片数据。

使用示例2：var base64data = geekapp.getImage(0, 0, 0.2, 0.1, 75); //获取网页左上角宽度2/10，高度1/10的矩形区域且质量为75的base64图片数据。

使用示例3：var base64data = geekapp.getImage(); //获取整个网页可见区域base64图片数据，默认图片质量75。

使用示例4：var base64data = geekapp.getImage(0, 0, 1, 1, 75); //获取整个网页可见区域base64数据。

说明：传入0-1的参数时(推荐)，默认以屏幕比例处理。>=1时以像素位置处理。图片质量取值范围1-100

#### 7.屏幕宽高接口名称：getWidth() 和 getHeight()

使用示例1：var w = geekapp.getWidth(); //获取网页可见区域宽度。

使用示例2：var h = geekapp.getHeight(); //获取网页可见区域高度。

说明：您也可以通过JS或Jquery接口获取。

# 代码示例
#### 模拟上滑手势/Simulate up slide gesture
```javascript
// ==UserScript==
// @name         Simulate up slide gesture
// @version      0.1
// @description  模拟手势上滑操作
// @author       Your Name
// @match        *
// @run-at       document-idle
// @grant        none
// ==/UserScript==
(function() {
  'use strict';
  //input your code
  setInterval(function(){
	
	//滑动/swipe
	geekapp.swipe(0.5, 0.8, 0.5, 0.2);
	console.log('swipe');
	
	//点击屏幕中央/Click the center
	//geekapp.click(0.5, 0.5);
	//console.log('click');
	
  }, 3000);
})();
```
