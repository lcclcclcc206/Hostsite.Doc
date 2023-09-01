## Vue

[Vue项目开发目录结构 - Halo_run - 博客园 (cnblogs.com)](https://www.cnblogs.com/chenleideblog/p/10432375.html)

[依赖注入 | Vue.js (vuejs.org)](https://cn.vuejs.org/guide/components/provide-inject.html)

[Vue中import引入模块路径时的@符号 - niceyoo - 博客园 (cnblogs.com)](https://www.cnblogs.com/niceyoo/p/10106035.html)

[事件处理 | Vue.js (vuejs.org)](https://cn.vuejs.org/guide/essentials/event-handling.html#key-modifiers)

[内置指令 | Vue.js (vuejs.org)](https://cn.vuejs.org/api/built-in-directives.html#v-bind)

## Vue Router

[介绍 | Vue Router (vuejs.org)](https://router.vuejs.org/zh/introduction.html)

[带参数的动态路由匹配 | Vue Router (vuejs.org)](https://router.vuejs.org/zh/guide/essentials/dynamic-matching.html)

[Vue Router 和 组合式 API | Vue Router (vuejs.org)](https://router.vuejs.org/zh/guide/advanced/composition-api.html)

[嵌套路由 | Vue Router (vuejs.org)](https://router.vuejs.org/zh/guide/essentials/nested-routes.html)

### 在 `setup` 中访问路由和当前路由

因为我们在 `setup` 里面没有访问 `this`，所以我们不能再直接访问 `this.$router` 或 `this.$route`。作为替代，我们使用 `useRouter` 和 `useRoute` 函数：

```js
import { useRouter, useRoute } from 'vue-router'

export default {
  setup() {
    const router = useRouter()
    const route = useRoute()

    function pushWithQuery(query) {
      router.push({
        name: 'search',
        query: {
          ...route.query,
          ...query,
        },
      })
    }
  },
}
```

`route` 对象是一个响应式对象，所以它的任何属性都可以被监听，但你应该**避免监听整个 `route`** 对象。在大多数情况下，你应该直接监听你期望改变的参数。

## Pinia

[定义 Store | Pinia (vuejs.org)](https://pinia.vuejs.org/zh/core-concepts/)