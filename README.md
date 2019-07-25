# 列表
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
