# Vue Router 知识点
###  JS
```javascript
npm i -S vue-router
import VueRouter from 'vue-router'
Vue.use(VueRouter)

const routes = [
    {
        path: '/a',
        component: A,
        redirect: '/a/aa'
    },
    {
        path: '/b',
        component: B,
        children: [
            {
                path: '/b/bb', // 普通路由的优先级比动态路由要高
                component: BB
            },
            {
                path: '/b/:id' // 动态路由
                component: BB
            }
        ]
    }

]

const router = new VueRouter({
    routes
})

export default router

// route 方法
// params
this.$route.params.id
// query
this.$route.query.message

// router 方法
// 路由跳转
this.$router.push({'/a/aa'})
// 带参数路由跳转
this.$router.push({
    path: '/a/aa',
    query: {
        message: 'hello'
    }
})
// 不向 Histroy 插入记录
this.$router.replace('/a/123')
// 回退
this.$router.go(-1)
```

###  HTML
```html
<router-view />
<router-link to="/a"></router-link>
```

