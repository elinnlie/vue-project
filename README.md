# 康护云 SaaS 数字化管理平台

> 这个项目是我在大二期间为了练手 Vue3 核心技术栈而开发的。从原本的一个陪诊练习，逐步重构成了支持多机构调度、权限隔离的 SaaS 平台原型。

### 🔗 [点这里在线预览](https://elinnlie.github.io/vue-project/)

## 🖼️ 运行截图
![Dashboard预览](./dashboard.png)

## 💡 我在这个项目里折腾了什么？
虽然这是一个后台管理系统，但我不仅是调包，还处理了一些工程细节：
* **权限这块**：没用死路由，而是根据登录后的 Role 动态 `addRoute` 挂载路由，前端也写了简单的权限校验。
* **状态持久化**：为了让 TagsView（多页签）刷新不丢失，我把 Vuex 的数据和 SessionStorage 做了同步。
* **部署流程**：自己折腾了 `gh-pages` 自动化发布，解决了 Vite 打包路径资源 404 的坑。
* **数据看板**：用 Echarts 做了个简单的聚合看板，处理了图表在侧边栏收缩时的自适应（ResizeObserver）。

## 🛠️ 怎么跑起来？
1. `npm install`
2. `npm run dev` (本地开发)
3. `npm run build` (打包发布)
