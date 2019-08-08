# 列表
## 单侧阴影
```
box-shadow: -7px 0 5px -5px #333;
```
## 正则获取url里的query
```
function getQuery(url) {
        var obj = {};
        url.replace(/([^?&=]+)=([^&#]+)/g, function (_, k, v) {
            obj[k] = v
        })
        return obj
    }
```
## 彩色图片转为黑白
```
.gray { 
    -webkit-filter: grayscale(100%);
    -moz-filter: grayscale(100%);
    -ms-filter: grayscale(100%);
    -o-filter: grayscale(100%);
    
    filter: grayscale(100%);
	
    filter: gray;
}
```
* 我们还可以直接在CSS,像图片一样引用SVG文件
```
.gray{
  -webkit-filter: grayscale(100%);
  filter: grayscale(100%);
  filter: gray;
  filter: url("data:image/svg+xml;utf8,<svg version='1.1' xmlns='http://www.w3.org/2000/svg' height='0'><filter id='greyscale'><feColorMatrix type='matrix' values='0.3333 0.3333 0.3333 0 0 0.3333 0.3333 0.3333 0 0 0.3333 0.3333 0.3333 0 0 0 0 0 1 0' /></filter></svg>#greyscale");
} 
```
## 固定宽高比例
  原理：padding的百分比是相对于其包含块的宽度，而不是高度
  ```
  ele{
        display: flex;
        width: 200px; //宽度随便写，高度会自适应
  }
   ele:after {
    content: '';
    padding-top: 56%; //16:9
  }
  ```
## 纯CSS实现滚动指示器
  1.在<body>标签内插入指示器元素：
```
<div class="indicator"></div>
```
  2.粘贴如下所示的CSS代码：
```
body {
    position: relative;
}
.indicator {
    position: absolute;
    top: 0; right: 0; left: 0; bottom: 0;
    background: linear-gradient(to right top, teal 50%, transparent 50%) no-repeat;
    background-size: 100% calc(100% - 100vh);
    z-index: 1;
    pointer-events: none;
    mix-blend-mode: darken;
}
.indicator::after {
    content: '';
    position: fixed;
    top: 5px; bottom: 0; right: 0; left: 0;
    background: #fff;
    z-index: 1;
}
```
