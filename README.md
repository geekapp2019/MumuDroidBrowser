# Mumu Browser 脚本浏览器
## GooglePlay下载地址：
https://play.google.com/store/apps/details?id=com.mumudroid.browser

## 国内镜像下载：
https://www.mumudroid.com/detail/115.html

## 在线接口文档
https://www.mumudroid.com/topic_detail/0111.html

## 支持Greasemonkey API（1，2，3）函数：
1. GM_addStyle
2. GM_deleteValue
3. GM_getResourceText
4. GM_getResourceURL
5. GM_getValue
6. GM_listValues
7. GM_log
8. GM_setValue
9. GM_xmlhttpRequest
10. GM_addElement
11. GM_info
12. GM_registerMenuCommand
13. GM_unregisterMenuCommand
## 支持Greasemonkey API（4）函数：
1. GM.addStyle
2. GM.deleteValue
3. GM.getResourceText
4. GM.getResourceURL
5. GM.getValue
6. GM.listValues
7. GM.log
8. GM.setValue
9. GM.xmlhttpRequest
10. GM.addElement
11. GM.info
12. GM.registerMenuCommand
13. GM.unregisterMenuCommand
## 扩展的Native原生函数：
1. GM_toast(text)
2. GM_click(x, y)
3. GM_swipe(x1, y1, x2, y2)
4. GM_getImage(left, top, width, height, quality)
5. GM_findOcrText(left, top, width, height, callback)
6. GM_findColor(color, offset, x_step, y_step, left, top, width, height, callback) 

备注：@run-at为main-thread时，脚本将在独立的容器中运行，稳定性更好，但是仅支持原生函数的调用。

## 代码示例
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
	GM_swipe(0.5, 0.8, 0.5, 0.2);
	console.log('swipe');
	
	//点击屏幕中央/Click the center
	//GM_click(0.5, 0.5);
	//console.log('click');
	
  }, 3000);
})();
```
## 屏幕坐标
<img src="screen_coordinates.jpg" width="320">
