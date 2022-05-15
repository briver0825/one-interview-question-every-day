# Hash 和 History

> 目前前端的一些 SPA 框架中都使用到了路由，由于 SPA 应用中的页面是依靠`Javascript` 生成的，所以不得不使用路由的方式进行切换页面

## Hash 模式

> Hash 即 网页路径 `#` 之后的内容，通过 `location.hash` 获取

- 改变 `hash` 不会导致浏览器刷新，但是改变的记录会在 `window.history` 中
- 可以通过 `window.onhashchange` 来监听 hash 的变化
- 由于 `hash` 只是客户端行为，不会产生请求，所以不会提交到服务端

## History 模式

> 可以通过 `history.pushState` 或 `location.replaceState` 这两个方法来进行切换 `history` ，其中 `location.replaceState` 是不进行记录的

- 通过改变 `history` 不会导致浏览器刷新，和产生请求
- `History` 模式可以传递 `state`
- 注意：使用 `History` 模式需要后端配合，更改 `nginx`配置，让页面请求都返回首页即可，否则用户手动刷新页面会导致出现`404` 的情况
