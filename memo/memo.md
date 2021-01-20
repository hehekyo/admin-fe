## 接口文档
[接口文档](https://gitee.com/imooccode/happymmallwiki)

## 基础知识

### cookie
在客户端保存用户信息
存储在本地的加密文件里，只有浏览器能操作
有域名和权限限制
cookie结构 [name,domain,path,expire,httpOnly]
    
    - 二级域名能操作一级域名的cookie，但是不能操作其他二级域名的cookie,
     也不能操作所属的三级域名的cookie
    - 同域名下不同路径的cookie不能操作
    - 如果不指定expire，会在一次会话完成后删除cookie，也就是在关闭浏览器后删除
    - httpOnly 用户端不能更改，只能在服务端设置
    
### session
在服务端保存请求信息

 - sessionid通常放在cookie，sessionid并不一定都是用cookie来实现的
   也可以是放在请求参数里，或者是放在http头的token里
 - 会话由浏览器控制，会话结束，session失效
 
```
添加cookie
 document.cookie='name=kyo'
```

### localStorage
有些信息只是记录用户偏好，不需要通过cookie带给服务器端，就适合存放在localstorage

- 只能在当前域名下使用
- 只接受key-value基本类型，key-object 不可，object会被变成string
- 没有过期时间

```
window.localStorage.setItem('name','Alex')

window.localStorage.getItem('name')

// 存对象数据需要用 JSON.stringify
window.localStorage.setItem('name',JSON.stringify({'name':'Henry'}))
```

### sessionStorage

- 关闭浏览器会消失


### 框架相关问题
什么是框架
框是约束，架是支撑
框架会控制我们书写代码时的各个部分的结构以及他们的依赖关系和交互流程
简单来说我们按照框架的要求来写我们的业务，而与业务无关的内容由框架帮我们来完成

#### 多页应用问题
- 路由体验问题
 访问新的页面需要重新加所有资源，耗时比较长，导致页面切换不流畅
- 无页面切换效果
- 浪费服务器资源


#### 单页应用优点
- 使用单页路由
html，js，css都不用重新加载
- 可以添加过场动画
- 减少服务器请求

#### 框架开发的不足

- 兼容性问题，SEO不友好
- 开发自由度低
- 框架本身有出错风险
- 有学习成本

#### 框架对比

- angular
  google 2009年

- react
  facebook 2013年开源 最新版本16.x
  - 基于js的视图层框架
    它可以把html，css都整合成js的一部分，将js作为整个应用的入口
    只关心页面的显示，不像angular MVC框架，数据也一起处理  
- vue
  2014年2月开源 尤雨溪 现加入阿里Weex团队
  主要版本 0.1x 1.x 2.x
  - 基于html的视图层框架 

框架对比

|          |Angular  | React | Vue.js|
|---------|---------|-------|-------|
|组织方式   |MVC      |   模块化 |   模块化|
|数据绑定 |双向绑定  |  单向绑定 | 双向绑定|
|模板能力   |强大     |   自由    | 简洁  |
|自由度   |较小     |   大    | 较大  |
|路由   |静态路由     |   动态路由   | 动态路由  |

做app ReactNative 最好, weex还不成熟


## 开发准备

### yarn和npm
yarn相比npm做了许多优化

### webpack
一个前端资源加载和打包工具
yarn add webpack@3.10.0 --dev

- plugin

html-webpack-plugin html单独打包成文件

extract-text-webpack-plugin 样式打包成单独文件

CommonChunkPlugin  提出通用模块

webpack-dev-server 为webpack提供web服务，更改代码自动刷新,不用手动执行
                  node_modules/.bin/webpack
                  
## React基础

### Router
页面Router
Hash Router 
H5 Router

```javascript
window.location.href='http://www.yahoo.co.jp'
window.location.href='#test1'
window.onhashchange = function(){console.log('current hash:',window.location.hash)}


//H5 Router
history.pushState('test','Title','#test3')
history.pushState('test','Title','/user/index')
window.onpopstate
history.replaceState('test','Title','/index/test')
```
### React Router

- 路由方式
BrowserRouter H5来实现的
HashRouter   hash来实现的
- 路由规则
Route 
- 路由选项
Switch
- 跳转导航
Link NavLink

- 自动跳转 
Redirect



```javascript


```






















    

    

    
    

