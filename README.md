<h1 align="center">Ant Design Pro</h1>

## 代码说明
折腾了很久,  ant-design-pro v4 包含所有Demo页面, 都没有成功, 最终用腾讯源成功了,所以记录下来形成仓库;
后面直接使用;

## 安装步骤
方法一:
```
nvm 切换为 v20.12.1
nrm 切换为 tencent
git clone  --depth=1 --branch v4.4.0  https://github.com/ant-design/ant-design-pro hello-antdpro
cd hello-antdpro
npm install
//fetch:blocks最后包含一步npm install会报错,所以需要再次npm install --legacy-peer-deps
SET NODE_OPTIONS=--openssl-legacy-provider && npm run fetch:blocks
npm install --legacy-peer-deps
npm start 
```

方法二:   

直接clone 带有package-lock.json的个人项目:      
https://github.com/ant-design/pro-blocks.git

## 方法一执行问题
### 问题1: 无法启动
```
// npm start 会报错, 如下, 原因是node版本太高;
opensslErrorStack: [
  'error:03000086:digital envelope routines::initialization error',
  'error:0308010C:digital envelope routines::unsupported'
],
  
// 修复办法, 在 package.json中添加使用传统ssl
"start": "SET NODE_OPTIONS=--openssl-legacy-provider && 原始命令",
```

### 问题2:所有区块Blocks安装
1. 用nrm 切换为 tencent 源, (ali源执行报错), 然后npm install
2. npm config set strict-ssl false
3. set NODE_TLS_REJECT_UNAUTHORIZED=0
4. npm cache clean --force
5. 修改github 相关host, 因为发现翻墙没用, 重点是这个api.github.com
6. 然后: SET NODE_OPTIONS=--openssl-legacy-provider && npm run fetch:blocks
7. 不行的话, 再开启代理重试set http_proxy=http://127.0.0.1:28888 & set https_proxy=http://127.0.0.1:28888
8. fetch:blocks最后包含一步npm install会报错,    
所以需要再次npm install --legacy-peer-deps


### 问题3:无法通过编译
改config/config.ts 中User改为小写
```
{
       path: '/user/login',
       name: 'login',
       component: './user/login',  // 改为小写
},
```



---   
---   
   



## 5.0 已经可以试用了 ! 🎉🎉🎉

[尝试 Ant Design Pro 5.0.0](https://beta-pro.ant.design/docs/upgrade-v5-cn)
- 预览：http://preview.pro.ant.design
- 首页：http://pro.ant.design/index-cn
- 使用文档：http://pro.ant.design/docs/getting-started-cn
- 更新日志: http://pro.ant.design/docs/changelog-cn
- 常见问题：http://pro.ant.design/docs/faq-cn
- 国内镜像：http://ant-design-pro.gitee.io

## 特性

- :bulb: **TypeScript**: 应用程序级 JavaScript 的语言
- :scroll: **区块**: 通过区块模板快速构建页面
- :gem: **优雅美观**：基于 Ant Design 体系精心设计
- :triangular_ruler: **常见设计模式**：提炼自中后台应用的典型页面和场景
- :rocket: **最新技术栈**：使用 React/umi/dva/antd 等前端前沿技术开发
- :iphone: **响应式**：针对不同屏幕大小设计
- :art: **主题**：可配置的主题满足多样化的品牌诉求
- :globe_with_meridians: **国际化**：内建业界通用的国际化方案
- :gear: **最佳实践**：良好的工程实践助您持续产出高质量代码
- :1234: **Mock 数据**：实用的本地数据调试方案
- :white_check_mark: **UI 测试**：自动化测试保障前端产品质量

## 模板

```
- Dashboard
  - 分析页
  - 监控页
  - 工作台
- 表单页
  - 基础表单页
  - 分步表单页
  - 高级表单页
- 列表页
  - 查询表格
  - 标准列表
  - 卡片列表
  - 搜索列表（项目/应用/文章）
- 详情页
  - 基础详情页
  - 高级详情页
- 用户
  - 用户中心页
  - 用户设置页
- 结果
  - 成功页
  - 失败页
- 异常
  - 403 无权限
  - 404 找不到
  - 500 服务器出错
- 帐户
  - 登录
  - 注册
  - 注册成功
```

## 使用

```bash
$ mkdir <your-project-name>
$ cd <your-project-name>
$ yarn create umi  # or npm create umi

# Choose ant-design-pro:
 Select the boilerplate type (Use arrow keys)
❯ ant-design-pro  - Create project with an layout-only ant-design-pro boilerplate, use together with umi block.
  app             - Create project with a simple boilerplate, support typescript.
  block           - Create a umi block.
  library         - Create a library with umi.
  plugin          - Create a umi plugin.

$ git init
$ npm install
$ npm start         # visit http://localhost:8000
```

更多信息请参考 [使用文档](http://pro.ant.design/docs/getting-started)。

## 支持环境

现代浏览器及 IE11。

| [<img src="https://raw.githubusercontent.com/alrra/browser-logos/master/src/edge/edge_48x48.png" alt="IE / Edge" width="24px" height="24px" />](http://godban.github.io/browsers-support-badges/)</br>IE / Edge | [<img src="https://raw.githubusercontent.com/alrra/browser-logos/master/src/firefox/firefox_48x48.png" alt="Firefox" width="24px" height="24px" />](http://godban.github.io/browsers-support-badges/)</br>Firefox | [<img src="https://raw.githubusercontent.com/alrra/browser-logos/master/src/chrome/chrome_48x48.png" alt="Chrome" width="24px" height="24px" />](http://godban.github.io/browsers-support-badges/)</br>Chrome | [<img src="https://raw.githubusercontent.com/alrra/browser-logos/master/src/safari/safari_48x48.png" alt="Safari" width="24px" height="24px" />](http://godban.github.io/browsers-support-badges/)</br>Safari | [<img src="https://raw.githubusercontent.com/alrra/browser-logos/master/src/opera/opera_48x48.png" alt="Opera" width="24px" height="24px" />](http://godban.github.io/browsers-support-badges/)</br>Opera |
| --- | --- | --- | --- | --- |
| IE11, Edge | last 2 versions | last 2 versions | last 2 versions | last 2 versions |

## 参与贡献

我们非常欢迎你的贡献，你可以通过以下方式和我们一起共建 :smiley:：

- 在你的公司或个人项目中使用 Ant Design Pro。
- 通过 [Issue](http://github.com/ant-design/ant-design-pro/issues) 报告 bug 或进行咨询。
- 提交 [Pull Request](http://github.com/ant-design/ant-design-pro/pulls) 改进 Pro 的代码。
