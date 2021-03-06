# 身份认证即服务

## 项目背景
身份认证与授权在Web系统中是一个非常基础的模块，几乎每个应用中都需要，然而为每个系统都实现一遍却是重复且冗余的工作，后期维护还不方便。因此业务系统多的会做一个自己SSO平台，用来统一管理身份认证这块，而国外有个[Auth0](https://auth0.com/)的服务提供商则在身份认证授权这块则做得更彻底、更专注，他们的产品相当于一个桥梁，免去中小型企业或个人项目开发身份认证模块，直接使用他们提供的API来完成认证和授权。国内虽然暂时没看到专注于这块的产品，但类似[LeanCloud](https://leancloud.cn/docs/leanstorage-started-js.html#_1_用户注册和登录)这样的产品也提供类似的功能。这个项目也是要做一个类似的产品，但肯定没有Auth0做的功能多。

## 术语约定
- `AAAS` 当前我们要开发的系统
- `用户` 使用我们`AAAS`系统的用户
- `应用` `用户`在我们的`AAAS`创建的应用
- `应用系统` 用户自己的实际应用项目
- `应用登录页面` 我们的`AAAS`系统为`应用系统`提供的登录页面，非`AAAS`的登录页面

## 项目需求
- 阶段一
  - 用户端
    `用户`登录`AAAS`后可以创建`应用`（包括应用名称，回调地址，白名单地址），创建后页面会给出一个`js`脚本文件以及该文件的引入方法和使用方法。`用户`将这段代码放到他们的页面中并进行一个配置就可以使用我们的服务。  
    当`用户`在`应用系统`中需要登录时，调用前面加入的`js`脚本暴露的`authorize`方法，该方法会自动判断当前用户是否已登录，如果已登录则执行`authorize`方法里的回调函数。如果未登录则跳转到`应用登录页面`，登录完成后返回`应用`配置的回调地址。  
  - 管理员端
    使用`AAAS`的管理员账号可以登录`AAAS`系统并查看用户统计、`应用`统计、登录区域统计等。

