# 移动端布局
## 移动端rem_layout

### 自接触移动端布局以来， 常见的几种自适应布局解决方案

1. 百分比布局
2. 百分比+弹性布局
3. rem font size of the root element

#### 各有千秋

* 百分比布局： 字体大小不好控制，需要另外一套自适应方案来解决；当屏幕宽度大于700px后，继续按照百分比计算的话，元素会偏大。
* flex布局：兼容性问题
* rem： 需要自己手动计算数值
#### what is the rem?
rem翻译过来就是font size of the root element. 它是通过js来根据当前的设备屏幕的宽度来改变font-size，页面元素就是根据html的font-size计算后> >p 的rem值来实现自适应缩放。
其实并不是页面上所有的元素都必须使用rem，比如底部导航可以固定高度，宽度使用flex弹性布局。

#### 偏爱rem
* 引用简单，布局方便，计算不算太难😄
* 根据设备像素比（DPPX），自动设置最合适的缩放
* 不同设备下的视觉体验都很赞。（之前的方案：屏幕越大元素越大。最新的方案： 屏幕越大，能看到的内容越多）

#### how to use

* rem只用于固定尺寸
* rem只用于固定尺寸
* rem只用于固定尺寸
言外之意： 并不是每个地方都用rem

最新的rem.js
```
<script>!function(e){function t(a){if(i[a])return i[a].exports;var n=i[a]={exports:{},id:a,loaded:!1};return e[a].call(n.exports,n,n.exports,t),n.loaded=!0,n.exports}var i={};return t.m=e,t.c=i,t.p="",t(0)}([function(e,t){"use strict";Object.defineProperty(t,"__esModule",{value:!0});var i=window;t["default"]=i.flex=function(normal,e,t){var a=e||100,n=t||1,r=i.document,o=navigator.userAgent,d=o.match(/Android[\S\s]+AppleWebkit\/(\d{3})/i),l=o.match(/U3\/((\d+|\.){5,})/i),c=l&&parseInt(l[1].split(".").join(""),10)>=80,p=navigator.appVersion.match(/(iphone|ipad|ipod)/gi),s=i.devicePixelRatio||1;p||d&&d[1]>534||c||(s=1);var u=normal?1:1/s,m=r.querySelector('meta[name="viewport"]');m||(m=r.createElement("meta"),m.setAttribute("name","viewport"),r.head.appendChild(m)),m.setAttribute("content","width=device-width,user-scalable=no,initial-scale="+u+",maximum-scale="+u+",minimum-scale="+u),r.documentElement.style.fontSize=normal?"50px": a/2*s*n+"px"},e.exports=t["default"]}]);  flex(false,100, 1);</script>

```

