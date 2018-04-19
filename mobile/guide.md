## 开发ISV插件的步骤
```plain
1. 申请AppKey
2. 开发应用插件
3. 发布上线
4. 提交审核
5. 上架服务市场
```

### 第一步：申请 AppKey
1. 在 [开放平台](https://open.1688.com/) 注册成为开发者
2. 创建应用，选择 应用类型，申请入驻到对应类目（需企业资质等条件）
3. 填写应用成功后，拿到 appkey

![image | left](https://gw.alicdn.com/tfs/TB1e4NDm49YBuNjy0FfXXXIsVXa-2608-1316.png "")


### 第2步： 开发应用插件

```plain
1. 安装本地开发工具 rap-cli 
2. 初始化 应用
3. 开发插件（本地开发对应的功能）
4. 提交代码
```

#### 安装插件本地开发工具 【 rap-cli 】
【下载地址】: 
[mac下载地址](http://rap-package.oss-cn-beijing.aliyuncs.com/rap.pkg)
[windows下载地址](http://rap-package.oss-cn-beijing.aliyuncs.com/rap.msi)

下载完成之后请安装 rap-cli 工具， 安装成功之后， 使用方式如下：

```bash
# 1. 初始化插件
rap init

# 2. 安装npm包
npm install 

# 本地启动
rap dev 

# 如果页面较多，可以通过上下箭头来选择需要编译的页面

```

### 第3步. 提交发布插件
* 平台上传  目前开始 预计5月底上线 
* 暂时先联系 @派朴(pipe.zkk)  内部协助发布

### 常见问题反馈：

  如何本地测试

1. 授权问题
2. 找不到对应的插件页面
3. rap.json的含义是？

