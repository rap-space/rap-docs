---
order: 1
title: 开发ISV插件的步骤
groupOrder: 1
group: 快速上手
---

# RAP

> 即【 Rox Application Package】的缩写。

<img src="https://img.alicdn.com/tfs/TB1ddy.m1uSBuNjSsziXXbq8pXa-685-595.png" width = "100" />

## Quick Start

#### 安装 CLI 工具

下载 `rap-cli` 安装包，点击运行安装包即可。下载的地址为[rap-cli/release](https://github.com/rap-space/rap-cli/releases/tag/1.0.0)。

#### 开发插件

安装完 `rap-cli` 后， 即可开始进行插件开发。 具体步骤如下：

```
# 初始化插件应用，并填入你申请的 AppKey（可忽略，之后再做修改）
$ rap init
$ rap dev
```

你也可以参考：[终端操作记录](https://asciinema.org/a/CnJg7kGxSugNysECVwRdNdudC)。

#### 主题

为了让组件在 1688 主客上正确的渲染出符合 1688 无线设计规范的样子，需要在页面最外层包裹一个 ThemeProvider：

```js
import { createElement, render, Component } from 'rax'
import { ThemeProvider, Button } from 'rox-components'

class App extends Component {
  render() {
    return (
      <ThemeProvider>
        <Button type="primary">你好，阿牛！</Button>
      </ThemeProvider>
    )
  }
}

render(<App />)
```

ThemeProvider 只是提供主题能力，本身并不会 产生内容，故无需担心嵌套层级的问题。

#### Done！🎉

在完成基础的插件开发。打开 [http://127.0.0.1:8888/demo/entry](http://127.0.0.1:8888/demo/entry) 页面，即可看到类似于以下界面：

![](https://img.alicdn.com/tfs/TB1592LoTtYBeNjy1XdXXXXyVXa-2038-390.png)

* 点击 `打开页面`，即能在游览器端查看、调试您所开发的页面
* 点击 `RAP-扫描测试`，使用阿里巴巴测试包扫描即可在端上查看页面效果

#### 阿里巴巴测试包下载

| iOS 测试包 | Android 测试包 |
| --- | --- |
| ![](https://img.alicdn.com/tfs/TB1FebVoHSYBuNjSspfXXcZCpXa-280-280.png) | ![](https://gw.alicdn.com/tfs/TB14WHNoQCWBuNjy0FaXXXUlXXa-280-280.png) |

## 插件创建流程

插件创建、管理、发布等流程均在 [阿里巴巴开放平台](https://open.1688.com/) 操作。

### 申请 AppKey

1. 在 [开放平台](https://open.1688.com/) 注册成为开发者
2. 创建应用，选择 应用类型，申请入驻到对应类目（需企业资质等条件）
> 如无线端插件可选择：应用工具 -> 商家端插件

3. 填写应用成功后，即可拿到 `Appkey`


### 发布上线

在开放平台上传代码包，上传完代码后提交审核，等待审核人员审核通过后上架服务市场，完成以上步骤即可完成上线。


> 插件可暂时先联系 @派朴(pipe.zkk) 内部协助发布。


## Rox-支持社区

如其他疑问的，可以扫描进群哈~

<img src="//img.alicdn.com/tfs/TB1CecNowmTBuNjy1XbXXaMrVXa-1242-1602.jpg" style="width: 400px;">
<!-- ![](https://img.alicdn.com/tfs/TB1CecNowmTBuNjy1XbXXaMrVXa-1242-1602.jpg) -->
