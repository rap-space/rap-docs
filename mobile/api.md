# RAP-SDK


# 页面导航类 RAP.navigator

页面导航用于控制页面的打开、返回、刷新、关闭等功能

## API 调用

### RAP.navigator.push(options)

打开跳转页面

#### API 调用入参
//todo

#### API 响应结果
//todo

#### 调用示例

```js
import RAP from 'rap-sdk';

RAP.navigator.push({
	url: 'https://www.1688.com', //新开页面 url
	title: '新开页面标题~',
	backgroundColor: '#ffffff', //新开导航栏背景颜色,
	clearTop: false, //新开页面后，是否关闭除了新页面之外的【所有其它(当前应用的)】页面
	animated: true, //<Boolean>: 切换时是否启用动画效果， 默认是 true 
}).then((result) => {
	console.log(result);
}).catch((error) => {
	console.log(error);
});
```

### RAP.navigator.pop(options)

关闭页面/后退

#### API 调用入参
//todo

#### API 响应结果
//todo

#### 调用示例

```js
//不传任何参数
import RAP from 'rap-sdk';

RAP.navigator.pop()
	.then((result) => { console.log(result);})
	.catch((error) => { console.log(error);});

//传入 index, animate
RAP.navigator.pop({
	index: 1,  //index >=1,
	animated: true //是否开启动画，默认为 true
}).then((result) => {
	console.log(result);
}).catch((error) => {
	console.log(error);
});

```

### RAP.navigator.popTo(options)

后退页面到指定索引或URL的页面

#### API 调用入参
//todo

#### API 响应结果
//todo

#### 调用示例

```js
import RAP from 'rap-sdk';

RAP.navigator.popTo({
   index: 1,
   animated: true  //默认 false
}).then(result => {
    console.log(result);
}).catch(error => {
    console.log(error);
})
```

### RAP.navigator.setTitle(options)

定制导航栏标题、按钮、菜单项等能力

#### API 调用入参
//todo

#### API 响应结果
//todo

#### 调用示例

```js
// 文字标题
import RAP from 'rap-sdk';

RAP.navigator.setTitle({
   text: '页面标题',
   color: '#fff600', //标题颜色
   url: 'https://www.1688.com' //点击标题跳转链接
}).then(result => {
    console.log(result);
}, error => {
    console.log(error);
});
```


### RAP.navigator.addRightItem(options, callback)

添加导航栏自定义按钮

#### API 调用入参
//todo

#### API 响应结果
//todo

#### 调用示例

```js
import RAP from 'rap-sdk';

//使用文字
RAP.navigator.addRightItem({
	text: "分享", //显示文字,
	tag: "share", //唯一标识，做删除用
}, () => {
	alert('点了分享按钮');
});

//文字图标同时存在的时候， 优先使用 iconImage
 RBridge.navigator.addRightItem({
 	text: '分享',
 	iconImage: 'https://gw.alicdn.com/tfs/TB17CV9XEgQMeJjy0FiXXXhqXXa-36-36.png',
 }, function () {
 // 这里是回调
 	window.alert('点了 旺旺');
 });
```

### RAP.navigator.removeRightItem(tagName);

去除自定义按钮

#### API 调用入参
//todo

#### API 响应结果
//todo

#### 调用示例

```js
RAP.navigator.removeRightItem('tagName') //根据tag 去除右侧自定义按钮
```

# 呼出拨号

呼出拨号

## API 调用

#### 调用示例

```js
import Link from 'rox-link';

<Link href="tel:114">拨打电话</Link>

```


# 剪切板 RAP.clipboard

## API 调用

### RAP.clipdoard.setString(options)

设置剪贴板文本数据

#### API 调用入参
//todo

#### API 响应结果
//todo

#### 调用示例

```js
import RAP from 'rap-sdk';

RAP.clipdoard.setString('我是设置的剪切板内容');
```

### RAP.clipdoard.getString(callback)

获取剪贴板文本数据

#### API 调用入参
//todo

#### API 响应结果
//todo

#### 调用示例

```js
import RAP from 'rap-sdk';

RAP.clipdoard.getString((res) => {
	console.log(res);
});
```



# 本地缓存 RAP.localstore


本地的持久化存储，有效范围为整个插件。

## API 调用

### RAP.localStorage.getItem(options);

#### API 调用入参
//todo

#### API 响应结果
//todo

#### 调用示例

```js
import RAP from 'rap-sdk';

RAP.localStorage.getItem({
	keys: ['key1', 'key2', 'key3']
}).then((result) => {
	console.log(result);
}).catch((error) => {
	console.log(error);
});

```


### RAP.localStorage.setItem(options);

#### API 调用入参
//todo

#### API 响应结果
//todo

#### 调用示例

```js
import RAP from 'rap-sdk';

RAP.localStorage.setItem({
	'a': 'aaaaaaaaaaaaaaaaaaaaa',
    'b': 'bbbbbbbbbbbbbbbbbbbbb',
    'c': 'ccccccccccccccccccccc'
}).then((result) => {
	console.log(result);
}).catch((error) => {
	console.log(error);
});

```


### RAP.localStorage.removeItem(options);

#### API 调用入参
//todo

#### API 响应结果
//todo

#### 调用示例

```js
import RAP from 'rap-sdk';

RAP.localstorage.removeItem({
	keys: ['key1', 'key2', 'key3']
}).then((result) => {
	console.log(result);
}).catch((error) => {
	console.log(error);
});
```


### RAP.localstorage.getKeys();


#### API 调用入参
//todo

#### API 响应结果
//todo

#### 调用示例

```js
import RAP from 'rap-sdk';

RAP.localStorage.getKeys()
	.then((result) => {console.log(result);})
	.catch((error) => {console.log(error);});
```


# 阿里旺旺 RAP.aliwangwang

阿里旺旺相关。

## API 调用

### RAP.aliwangwang.openChat(options);

//原始 API:

```js
RapBriage.call('aliwangwang', 'openChat', {
	loginId: '123'
}, successCallback, failureCallback, notify);
```

#### API 调用入参

| 名称     | 类型      | 默认值   |  说明   |
| -------- | -------- | -------- |--------|
| loginId  | String   |          |	中文站旺旺id|	

#### API 响应结果
//todo

#### 调用示例

```js
import RAP from 'rap-sdk';

RAP.aliwangwang.openChat('用户 loginId')
	.then(result => console.log(result))
	.catch(error => console.log(error))
```


### aliwangwang.sendMessage(options)

//原始 API

```js
RapBriage.call('aliwangwang', 'sendMessage', {
	loginId: '123',
	message: '消息内容'
}, successCallback, failureCallback, notify);
```

#### API 调用入参

| 名称     | 类型      | 默认值   |  说明   |
| -------- | -------- | -------- |--------|
| loginId  | String   |          |中文站旺旺id|
| message  | String   |          | 消息内容|

#### API 响应结果
//todo

#### 调用示例

```js
import RAP from 'rap-sdk';

RAP.aliwangwang.sendMessage({
	loginId: '123',
	message: '消息内容'
}).then(result => console.log(result))
  .catch(error => console.log(error))
```

### aliwangwang.isLogin(options)


//原始 API:

```js
RapBriage.call('aliwangwang', 'isLogin', {
	loginId: '123'
}, successCallback, failureCallback, notify);
```

#### API 调用入参

| 名称     | 类型      | 默认值   |  说明   |
| -------- | -------- | -------- |--------|
| loginId  | String   |          |	中文站旺旺id|	

#### API 响应结果
//todo

#### 调用示例

```js

import RAP from 'rap-sdk';

RAP.aliwangwang.isLogin({
	loginId: '123'
}).then(result => console.log(result))
  .catch(error => console.log(error))
  
```
  

# 事件相关 RAP.on/emit/off

事件调用

## API 调用

### RAP.on

绑定、监听事件

#### API 调用入参
//todo

#### API 响应结果
//todo

#### 调用示例

```js
RAP.on('Page.hello', (data) => {
    console.log(data);
});

// 如果需要关注事件注册的结果是成功还是失败
RAP.on('App.hello', (data) => {
    console.log(data);
})
.then(result => {
    console.log('注册成功');
})
.catch(error => {
    console.log('注册失败');
});
```

### RAP.emit

触发事件

#### API 调用入参
//todo

#### API 响应结果
//todo

#### 调用示例

```js
let data = {msg: 'msg from Page.hello'};
// 仅触发事件
RAP.emit('Page.hello');

// 触发事件，并发送数据
RAP.emit('Page.hello', data);

// 触发事件，并希望得知触发是否成功
RAP.emit('Page.hello')
.then(result => {
    console.log('触发成功');
})
.catch(error => {
    console.log('触发失败');
});
```

### RAP.off

解绑、注销事件

#### API 调用入参
//todo

#### API 响应结果
//todo

#### 调用示例

```js
// 注销事件时传递对应的回调函数。此时只会注销该回调函数，其他的事件回调函数不受影响。
RAP.off('Page.hello', (data) => {
    console.log(data);
});
// 注销事件时不传递事件回调函数，此时会注销所有该事件下的回调函数。
RAP.off('Page.hello');

// 如果需要关注注销事件的结果是成功还是失败
RAP.off('App.hello', (data) => {
    console.log(data);
})
.then(result => {
    console.log('注销成功');
})
.catch(error => {
    console.log('注销失败');
});
```

## RAP.pluginManage

rap 插件管理

### RAP.pluginManage.updatePluginList()

更新插件列表

//原始调用

```js
//更新插件列表
RBbridge.call('PluginManage', 'updatePluginList', {}, successCallback, failureCallback);
```

#### API 调用入参
//todo

#### API 响应结果
//todo

#### 调用示例

```js

```

### RAP.pluginManage.setPluginsGray(Appkeys)

设置插件灰度 

//原始调用
```js
//设置插件灰度
RBbridge.call('PluginManage', 'setPluginsGray', {
	appKeys: [1, 2, 3]
}, successCallback, failureCallback);
```

#### API 调用入参
//todo

#### API 响应结果
//todo

#### 调用示例

```js

```


