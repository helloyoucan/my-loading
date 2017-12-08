# my-loading
一个loading插件，用于ajax时的loading显示

#### 效果图

![](http://opok8iwaa.bkt.clouddn.com/image/github/my-loading/my-loading-show.png)

#### 示例代码

```html
<div id="test-div" style="width: 500px;height: 500px;background-color: #e5e5e5;"></div>
```



```javascript
//var l = new MyLoading();
var l = new MyLoading({ //这里是全局配置,下面的都是默认选项
	id: 'my-loading', //loading的唯一标记,用于区分loading,默认为这个
	type: 'round', //round,bar，两种风格
	background: 'transparent', //loading时的背景
	text: '', //提示文字
	textColor: '#000', //提示文字的颜色
	afterHideLoadingOverflow: 'auto', //隐藏loading后容器的style的Overflow值
	beforeShow: function() {},
	afterShow: function() {},
	beforeHide: function() {},
	afterHide: function() {},
});
//两种方式打开loading
l.show(document.getElementById('test-div'), { //参数1为loading的容器元素，参数2为配置单个loading，下面的都是默认选项
	id: 'test', //loading的唯一标记,用于区分多个loading的情况，单个时可不传
	type: 'round', //round,bar
	background: 'transparent', //loading时的背景
	text: '', //提示文字
	textColor: '#000', //提示文字的颜色
	beforeShow: function() {},
	afterShow: function() {},
});
//l.show(document.getElementById('test-div'));
setTimeout(function() {
	//两种方式关闭loading,如果前面的l.show()没有传id，就同样不要传id，如果非要传，就传默认的'my-loading'
	l.hide({
		id: 'test',
		afterHideLoadingOverflow: 'auto', //隐藏loading后容器的style的Overflow值
		beforeHide: function() {},
		afterHide: function() {},
	});
	//l.hide('test');
}, 3000);
//l.destroy(); //销毁，把关于loading的style都remove掉
```

