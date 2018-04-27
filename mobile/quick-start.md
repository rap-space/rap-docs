---
order: 1
title: RAP
groupOrder: 1
group: 快速上手
---





使用 客户端扫码 预览



Rox 是一套基于 Rax/Weex 且符合 1688 客户端无线设计规范的组件库，服务于 ISV 开发者快速开发应用并入驻到 1688 开放平台。



## 快速开始

#### 安装 rap 工具

 `rap-cli`



如何使用
安装
通过 npm 安装最新版本 Rox 组件：rox-components

npm install --save rox-components
使用

目前 rox-components 中可用的组件有：

Button

Checkbox

Icon

Input

NumberPicker

Progress

SearchBar

Slip

Switch

Text

Theme

ThemeProvider

View

其中几乎每一个组件都可以直接对标 NukeUI 的组件，相关 API 和 NukeUI 的 API 完全一致，组件文档可暂时参考 NukeUI 的 API 文档。

主题
为了让组件在 1688 主客上正确的渲染出符合 1688 无线设计规范的样子，需要在页面最外层包裹一个 ThemeProvider：

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
ThemeProvider 只是提供主题能力，本身并不会 产生内容，故无需担心嵌套层级的问题。