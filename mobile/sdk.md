<a name="RAP"></a>

## RAP : <code>object</code>
**类型**: 全局命名空间(namespace)

* [RAP](#RAP) : <code>object</code>
    * [.app](#RAP.app)
    * [.on](#RAP.on)
    * [.off](#RAP.off)
    * [.emit](#RAP.emit)
    * [.navigator](#RAP.navigator)
    * [.localStorage](#RAP.localStorage)
    * [.user](#RAP.user)
    * [.fetch](#RAP.fetch)
    * [.aop](#RAP.aop)
    * [.share](#RAP.share)
    * [.toast](#RAP.toast)
    * [.aliwangwang](#RAP.aliwangwang)
    * [.showLoading](#RAP.showLoading)
    * [.hideLoading](#RAP.hideLoading)
    * [.clipboard](#RAP.clipboard)
    * [.sso](#RAP.sso)
    * [.env](#RAP.env)

<a name="RAP.app"></a>

### RAP.app
APP探测环境相关

**类型**: 静态属性(property)，来自 [<code>RAP</code>](#RAP)

| 参数 | 类型 | 描述 |
| --- | --- | --- |
| isIOS | `boolean` | 是否是IOS系统 |
| isAndroid | <code>boolean</code> | 是否是Android系统 |
| version | <code>string</code> | 主客APP的版本号 |
| ua | <code>string</code> | UserAgent相关信息 |

**示例**
```js
RAP.app.isIOS
RAP.app.isAndroid
RAP.app.version
RAP.app.ua
```
<a name="RAP.on"></a>

### RAP.on
绑定, 监听事件

**类型**: 静态属性(property)，来自 [<code>RAP</code>](#RAP)

| 参数 | 类型 | 描述 |
| --- | --- | --- |
| eventName | <code>string</code> | 事件名称 |
| callback | <code>function</code> | 回调函数 |

**示例**
```js
// RAP.on
// 绑定监听事件

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
<a name="RAP.off"></a>

### RAP.off
解绑, 注销事件

**类型**: 静态属性(property)，来自 [<code>RAP</code>](#RAP)

| 参数 | 类型 | 描述 |
| --- | --- | --- |
| eventName | <code>string</code> | 事件名称 |
| callback | <code>function</code> | 回调函数 |

**示例**
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
<a name="RAP.emit"></a>

### RAP.emit
触发事件

**类型**: 静态属性(property)，来自 [<code>RAP</code>](#RAP)

| 参数 | 类型 | 描述 |
| --- | --- | --- |
| eventName | <code>string</code> | 事件名称 |
| data | <code>object</code> | 传递参数 |

**示例**
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
<a name="RAP.navigator"></a>

### RAP.navigator
导航类方法

**类型**: 静态属性(property)，来自 [<code>RAP</code>](#RAP)

| 参数 | 类型 | 描述 |
| --- | --- | --- |
| push | <code>function</code> | 打开跳转页面 |
| pop | <code>function</code> | 关闭/后退页面 |
| popTo | <code>function</code> | 后退页面到指定索引或URL的页面 |
| setTitle | <code>function</code> | 定制导航栏标题 |
| addRightItem | <code>function</code> | 添加导航栏自定义按钮 |
| removeRightItem | <code>function</code> | 移除导航栏自定义按钮 |

**示例**
```js
// RAP.navigator.push
// 打开跳转页面

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
**示例**
```js
// RAP.navigator.pop
// 关闭页面/后退

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
**示例**
```js
// RAP.navigator.popTo
// 后退页面到指定索引或URL的页面

RAP.navigator.popTo({
  index: 1,
  animated: true  //默认 false
}).then(result => {
  console.log(result);
}).catch(error => {
  console.log(error);
});
```
**示例**
```js
// RAP.navigator.setTitle
// 定制导航栏标题

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
**示例**
```js
// RAP.navigator.addRightItem
// 添加导航栏自定义按钮

//使用文字
RAP.navigator.addRightItem({
  text: "分享", //显示文字,
  tag: "share", //唯一标识，做删除用
}, () => {
  alert('点了分享按钮');
});

//文字图标同时存在的时候， 优先使用 iconImage
RAP.navigator.addRightItem({
  text: '分享',
  iconImage: 'https://gw.alicdn.com/tfs/TB17CV9XEgQMeJjy0FiXXXhqXXa-36-36.png',
}, function () {
  window.alert('点了 旺旺');
});
```
**示例**
```js
// RAP.navigator.removeRightItem
// 去除自定义按钮

RAP.navigator.removeRightItem('tagName')  //根据tag 去除右侧自定义按钮
```
<a name="RAP.localStorage"></a>

### RAP.localStorage
本地持久化
本地的持久化存储，有效范围为整个插件

**类型**: 静态属性(property)，来自 [<code>RAP</code>](#RAP)

| 参数 | 类型 | 描述 |
| --- | --- | --- |
| getItem | <code>function</code> | 获取数据 |
| setItem | <code>function</code> | 存储数据 |
| removeItem | <code>function</code> | 删除数据 |
| getKeys | <code>function</code> | 获取已有存储数据键 |

**示例**
```js
// RAP.localStorage.getItem
// 获取数据

RAP.localStorage.getItem({
  keys: ['key1', 'key2', 'key3']
}).then((result) => {
  console.log(result);
}).catch((error) => {
  console.log(error);
});
```
**示例**
```js
// RAP.localStorage.setItem
// 存储数据

RAP.localStorage.setItem({
  a: 'aaaaaaaaaaaaaaaaaaaaa',
  b: 'bbbbbbbbbbbbbbbbbbbbb',
  c: 'ccccccccccccccccccccc'
}).then((result) => {
  console.log(result);
}).catch((error) => {
  console.log(error);
});
```
**示例**
```js
// RAP.localStorage.removeItem
// 删除数据

RAP.localStorage.removeItem({
  keys: ['key1', 'key2', 'key3']
}).then((result) => {
  console.log(result);
}).catch((error) => {
  console.log(error);
});
```
**示例**
```js
// RAP.localStorage.getKeys
// 获取已存储的键

RAP.localStorage.getKeys()
  .then((result) => {console.log(result);})
  .catch((error) => {console.log(error);});
```
<a name="RAP.user"></a>

### RAP.user
用户状态信息相关

**类型**: 静态属性(property)，来自 [<code>RAP</code>](#RAP)

| 参数 | 类型 | 描述 |
| --- | --- | --- |
| getUserInfo | <code>function</code> | 获取用户登录状态 |
| login | <code>function</code> | 登录 |
| logout | <code>function</code> | 登出 |

**示例**
```js
// RAP.user.getUserInfo
// 获取用户登录状态和用户信息

RAP.user.getUserInfo()
.then((result) => {
  console.log(result);
})
.catch((error) => {
  console.log(error)
})；

// 获取额外的用户信息
RAP.user.getUserInfo({ extraInfo: true })
.then((result) => {
  console.log(result);
})
.catch((error) => {
  console.log(error)
})；
```
**示例**
```js
// RAP.user.login
// 拉起登录

RAP.user.login()
.then((result) => {
  console.log(result);
})
.catch((error) => {
  console.log(error)
});
```
**示例**
```js
// RAP.user.logout
// 拉起登出

RAP.user.logout()
.then((result) => {
  console.log(result);
})
.catch((error) => {
  console.log(error)
})；
```
<a name="RAP.fetch"></a>

### RAP.fetch
fetch (RAX中的网络请求方法)

**类型**: 静态属性(property)，来自 [<code>RAP</code>](#RAP)

| 参数 | 类型 | 描述 |
| --- | --- | --- |
| url | <code>string</code> | 请求地址 |
| option(method) | <code>string</code> | 资源请求方法('GET'|'POST') |
| option(mode) | <code>string</code> | 请求模式（cors, no-cors, same-origin 和 jsonp） |
| option(dataType) | <code>string</code> | 资源类型（仅在weex下支持，包括json和text两种) |
| option(body) | <code>string</code> | 请求体 |
| option(header) | <code>object</code> | 请求头 |

**示例**
```js
fetch('./api.json', {
  mode: 'same-origin',
  dataType: 'json',
  method: 'GET'
})
.then((response) => {
  return response.json();
})
.then((data) => {
  console.log(data);
})
.catch((err) => {
// handle exception
});
```
<a name="RAP.aop"></a>

### RAP.aop
网络请求相关

**类型**: 静态属性(property)，来自 [<code>RAP</code>](#RAP)

| 参数 | 类型 | 描述 |
| --- | --- | --- |
| request | <code>function</code> | 发送MTOP请求 |
| proxy | <code>function</code> | 发送代理请求 |

**示例**
```js
// RAP.aop.request
// 发送请求

const requestParams = {
  namespace: "cn.alibaba.open",
  api: "userCategory.offers.remove",
  version: "1",
  params: JSON.stringify({"offerIds":"564985083537","groupId":"96005556"})
}
// MTOP请求
RAP.aop.request(requestParams)
.then((data) => {
  console.log(data);
})
.catch((error) => {
  console.log(error);
})
```
**示例**
```js
// RAP.aop.proxy
// 发送代理请求

const requestParams = {
  method: 'GET',
  url: 'https://devweb1688.aiyongbao.com/Autoresend/getNoResProduct?ayServer=true&sellernick=上海爱用宝软件'
}

//发送代理请求
RAP.aop.proxy(requestParams)
.then((data) => {
  console.log(data);
})
.catch((error) => {
  console.log(error);
})
```
<a name="RAP.share"></a>

### RAP.share
调用分享

**类型**: 静态属性(property)，来自 [<code>RAP</code>](#RAP)
**示例**
```js
const url = 'http://cui.m.1688.com/weex/weex_dacu/3139.html?__positionId__=weex_dacu&__pageId__=3139&__weex__=true';
const picUrl = 'https://gw.alicdn.com/tfs/TB1isFOcgMPMeJjy1XcXXXpppXa-750-473.jpg_10000x340q60.jpg';

RAP.share({
  title: '这里是分享标题',
  url: url,
  picUrl: picUrl,
  content: '这里是分享内容这里是分享内容这里是分享内容',
  webUrl: url,
  formWhere: 'formWhere',
  companyName: 'companyName',
  leftButtonName: '左按钮',
  rightButtonName: '右按钮',
  address: 'address',
  // 分享到web的时候
  template: '推荐一个不错的商品，分享口令 @shareToken@，点击链接：@shareUrl@',

  // typeQr: 当isUserToken 为false 的时候可用， WEB 【text, imgtext, web】
  typeQr: 'text',
  isUserToken: true
});
```
<a name="RAP.toast"></a>

### RAP.toast
提示信息

**类型**: 静态属性(property)，来自 [<code>RAP</code>](#RAP)

| 参数 | 类型 | 描述 |
| --- | --- | --- |
| show | <code>function</code> | 显示消息 |

**示例**
```js
RAP.toast.show('Hi'); // 默认是RAP.toast.SHORT
RAP.toast.show('Hello', RAP.toast.SHORT); // 2秒
RAP.toast.show('Hello', RAP.toast.LONG);  // 3.5秒
```
<a name="RAP.aliwangwang"></a>

### RAP.aliwangwang
阿里旺旺

**类型**: 静态属性(property)，来自 [<code>RAP</code>](#RAP)

| 参数 | 类型 | 描述 |
| --- | --- | --- |
| openChat(userID) | <code>function</code> | 打开阿里旺旺聊天 |
| userID | <code>string</code> | 旺旺ID |
| sendMessage(option) | <code>function</code> | 发送消息 |
| option | <code>object</code> | 发送消息参数 |

**示例**
```js
// RAP.aliwangwang.openChat
// 打开旺旺聊天

RAP.aliwangwang.openChat("用户 旺旺ID")
.then((result) => {
  console.log(result);
}).catch((error) => {
  console.log(error);
});
```
**示例**
```js
// RAP.aliwangwang.sandMessage
// 发送消息

RAP.aliwangwang.sendMessage({
  loginId: '123',  //旺旺id
  message: '消息内容'
})
.then(result => console.log(result))
.catch(error => console.log(error))
```
**示例**
```js
// RAP.aliwangwang.isLogin
// 判断是否登录

RAP.aliwangwang.isLogin({
  loginId: '123'
})
.then(result => console.log(result))
.catch(error => console.log(error))
```
<a name="RAP.showLoading"></a>

### RAP.showLoading
显示加载动画

**类型**: 静态属性(property)，来自 [<code>RAP</code>](#RAP)

| 参数 | 类型 | 描述 |
| --- | --- | --- |
| option(text) | <code>string</code> | 加载文本 |
| option(iconImage) | <code>string</code> | 加载图片 |

**示例**
```js
RAP.showLoading({
 iconImage: '',
 text: "加载中..."
});
```
<a name="RAP.hideLoading"></a>

### RAP.hideLoading
隐藏加载动画

**类型**: 静态属性(property)，来自 [<code>RAP</code>](#RAP)
**示例**
```js
RAP.hideLoading();
```
<a name="RAP.clipboard"></a>

### RAP.clipboard
剪贴板

**类型**: 静态属性(property)，来自 [<code>RAP</code>](#RAP)

| 参数 | 类型 | 描述 |
| --- | --- | --- |
| getString | <code>function</code> | 获取剪贴板文本数据 |

**示例**
```js
// RAP.clipdoard.getString
// 获取剪贴板文本数据

RAP.clipdoard.getString((res) => {
  console.log(res);
});
```
<a name="RAP.sso"></a>

### RAP.sso
授权

**类型**: 静态属性(property)，来自 [<code>RAP</code>](#RAP)

| 参数 | 类型 | 描述 |
| --- | --- | --- |
| goAuth | <code>function</code> | 调用授权 |

**示例**
```js
RAP.sso.goAuth();
```
<a name="RAP.env"></a>

### RAP.env
运行时环境相关

**类型**: 静态常量(const)，来自 [<code>RAP</code>](#RAP)

| 参数 | 类型 | 描述 |
| --- | --- | --- |
| isWeex | <code>boolean</code> | 是否在weex环境下 |
| isWeb | <code>boolean</code> | 是否在web环境下 |

**示例**
```js
if(RAP.env.isWeex) {
  //...
}

if(RAP.env.isWeb){
  //...
}
```
