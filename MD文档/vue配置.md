#### 配置

<br/>

##### 临时使用

`npm --registry https://registry.npm.taobao.org install express`

##### 永久使用

`npm config set registry https://registry.npm.taobao.org`

##### 恢复原来官方地址

`npm install -g cnpm --registry=https://registry.npm.taobao.org`

<br/>

#### 安装vue-cli

`npm install -g @vue/cli      `//全局安装 vue-cli

##### >cli2 创建项目

`vue create 项目名称`

`npm run serve`		“启动项目”



#####  cli2 创建项目

如果要使用旧版本的 vue init 功能，你可以全局安装一个桥接工具：

`npm i -g @vue/cli-init`  

`vue init webpack 项目名称`  

`npm install`		“安装依赖”

`npm run dev`		“启动项目”



打包项目

但是此时我们打开index.html.确实白屏。

这是vue 3.X的问题。所以需要我们在根目录下新建 vue.config.js 并输入：

```javascript
module.exports = {
    publicPath: './'
}
```

之后，打开router/index.js 将

```javascript
const router = new VueRouter({
  mode: 'history',
  base: process.env.BASE_URL,
  routes
})
```

##### `mode: 'history',`注释掉。

这就涉及到路由的模式了，之后有机会再编写。此时注释掉相当于mode:hash。

之后再打包，即可成功。