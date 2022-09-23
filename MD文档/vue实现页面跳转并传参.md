## vue实现页面跳转并传参

### 声明

vue中每个页面都需要在路由中声明，就是在router/index.js中写下面代码：

```js
import Vue from 'vue'
import Router from 'vue-router'
import Test from "../components/Test";
Vue.use(Router)
export default new Router({
  mode: 'history',
  routes: [
		  {
		      path: '/t',
		      name: 'Test',
		      component: Test,
		      hidden:true
		    },
    	]
    })
```

### 实现

#### HTML

1. 在template中可以使用`<router-link>`标签实现跳转，跳转的路径是http://localhost:8080/t?index=id，如下：

   ```html
   <router-link to="/t?index=1">
        <button class="btn btn-default">点击跳转</button>
   </router-link>
   ```

   只需要点击按钮就可以实现跳转，不需要写js代码，需要传递参数的话只需要`/t?index=1`即可，这样的话跳转的页面获取参数通过`window.location.href`能够获取到完整的url,然后截取参数。也可以通过下面代码获取参数

   `this.$route.query.index`

2. 跳转的路径是http://localhost:8080/t?index=id

   ```html
   <router-link :to="{path:'/t',query: {index: 1}}">
        <button class="btn btn-default">点击跳转</button>
   </router-link>
   ```

   其中需要注意，这里的to前面一定要加冒号，path的值要和上面路由定义的值一致，传参用query，里面是参数字典。 接收参数：

   `this.$route.query.index`

3. 命名路由的方式： 跳转的路径是http://localhost:8080/t?index=id

   ```html
   <router-link :to="{name:'Test',params: {index: 1}}">
        <button class="btn btn-default">点击跳转</button>
   </router-link>
   ```

   注意这里的name也要和router/index.js中声明的name值一致，并且传参使用params，和name配对的是params，和path配对的是query。 接收参数：

   `this.$route.params.index`

4. 跳转的路径是http://localhost:8080/t/id

   ```html
   <router-link:to="'/test/'+1">
        <button class="btn btn-default">点击跳转</button>
   </router-link>
   ```

   这时的路由也需要更为为下面的形式：

   ```js
   routes: [
   		  {
   		      path: '/t/:index',
   		      name: 'Test',
   		      component: Test,
   		      hidden:true
   		    },
       	]
   ```

   接收参数：

   `this.$route.params.index`

#### JS

1. 上面四种方法都是在html中实现的跳转，还有另外对应的在js中实现的跳转并传参的方法，代码如下：

   ```vue
   <template>
   <button @click = "func()">跳转</button>
   </template>
   <script>
       export default{
           methods:{
               func (){
                   this.$router.push({path: '/t?index=1'});
               }
           }
       }
   </script>
   ```

   接收参数依然使用:

   `this.$route.query.index`

2. ```vue
   <template>
   <button @click = "func()">跳转</button>
   </template>
   <script>
       export default{
           methods:{
               func (){
                   this.$router.push({path: '/t',query:{ index:'1'}});
               }
           }
       }
   </script>
   ```

   接收参数依然使用:

   `this.$route.query.index`

3. ```vue
   <template>
   <button @click = "func()">跳转</button>
   </template>
   <script>
       export default{
           methods:{
               func (){
                   this.$router.push({path: '/t/index'});
               }
           }
       }
   </script>
   ```

   接收参数依然使用:

   `this.$route.query.index`

4. ```vue
   <template>
   <button @click = "func()">跳转</button>
   </template>
   <script>
       export default{
           methods:{
               func (){
                   this.$router.push({name: 'Test',params:{ index:'1'}});
               }
           }
       }
   </script>
   ```

   接收参数依然使用:

   `this.$route.params.index`