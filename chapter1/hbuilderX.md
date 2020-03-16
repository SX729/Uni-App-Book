# HBuilderX快捷开发与常规使用
## 快捷开发：
### 1. 调试快捷键
- ctrl + r 运行到小程序模拟器
- ctrl + F5 编辑后重新运行

### 2. 标签快捷键
- uList / uListMedia 快速创建列表

### 3. js快捷键
- uRequest 快速创建接口请求代码块
- Vue method vue自定义方法代码块
- unav激活uni.navigateTo 快速路由跳转代码块
- ushowload 增加加载动画

## 常规使用：
### 1. 标签数据绑定
&emsp;&emsp;:data-* 其中*为小写变量，如newsid
### 2. @事件获取标签数据
&emsp;&emsp;e.currentTarget.dataset.newsid
### 3. 路由跳转：
- [navigator](https://uniapp.dcloud.io/component/navigator?id=navigator)标签进行跳转

- 绑定单机事件 @tap，事件中uni.navigateTo
  > @tap与@click：
  >
  > &emsp;&emsp;click事件是pc端的单机事件，但是当这个事件在移动端实现的时候，点击放开之后才触发的，会出现延迟300ms的现象，所以移动端一般用tap来代替click。
  >
  > &emsp;&emsp;tap是Zepto.js针对移动端设计的高级JS浏览器库中的事件，可以减少click在移动端的延迟，提高了性能。但是存在『事件穿透』现象，就是你执行完绑定的tap事件之后呢，如果下面如果绑定了其他事件或者是本身就存在点子事件的话（a/input），也会默认触发。(解决：fastclick.js，或者为元素绑定touchend事件，并在内部加上e.preventDefault())
  > 
  >@tap像click事件一样可以获取event : @tap="Isinspect('普通参数',$event)", event.currentTarget 
  >
  时间冒泡处理： @click.stop
  
### 4. 加载动画：
```
  uni.showLoading({
    title: '加载中'
  });
  uni.hideLoading()
```
### 5. 只模拟某个页面开发时：
&emsp;&emsp;pages.json里的pages会放置页面路径及窗口表现，此外还有一个condition启动模式配置，仅开发期间生效，用于模拟直达页面的场景，如：小程序转发后，用户点击所打开的页面。
```
  "pages": [],
	"condition": {
		"current": 0, //当前激活的模式
		"list": [{
			"name": "test",
			"path": "pages/info/info",
			"query":"newsid=5158607"
		}]	
	}
```