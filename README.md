# 天小塔（TianXiaoTa）前端静态站点

该目录是“天小塔”前端静态页面集合（可直接用任意静态服务器托管）。项目通过 `index.html` 作为入口页，并包含科研/文献等智能体中心页与绘图智能体子站点。

## 目录结构

- `index.html`：主页面（含顶部 Logo 区域、入口卡片跳转、访问/使用统计等）
- `assets/`：打包后的前端资源（`index-*.js`、`index-*.css`）
- `Ta-Logo.png`：天小塔副 Logo（用于主页面顶部）
- `research_center.html`：科研写作智能体中心页
- `academic_center.html`：学术文献智能体中心页
- `AI_Draw/`：科研绘图智能体子站点（独立的 `index.html` + 素材）

## 本地运行

在项目根目录启动静态服务器即可：

```bash
python3 -m http.server 5137
```

打开：

- `http://localhost:5137/`

## 页面入口与跳转

- 主页面：`/index.html`
- 科研写作智能体中心：`/research_center.html`
- 学术文献智能体中心：`/academic_center.html`
- 科研绘图智能体：`/AI_Draw/index.html`

主页面部分入口会跳转到外部系统（例如学科大模型对话、实验计算助手等），对应链接在页面脚本中维护。

## 访问/使用次数统计（本地存储）

项目在前端实现了两类计数，并存储在浏览器 `localStorage`：

- **访问次数**：页面每次打开计数 `+1`
- **智能体使用次数**：点击智能体入口/对话框等触发 `+1`

统计会在页面右下角浮窗展示（同一浏览器/同一设备内持久化）。

### localStorage 键

- `tianxiaota.metrics.visitCount`：累计访问次数
- `tianxiaota.metrics.agentUseCount`：累计智能体使用次数
- `tianxiaota.metrics.agentUseByName`：按智能体名称汇总的使用次数（JSON）
- `tianxiaota.metrics.logs`：最近的访问/使用记录（JSON，默认保留最近 200 条）

## 开发说明（重要）

- `assets/index-*.js` 为打包产物（通常来自 React/Vite 构建结果）。
- 当前项目为了快速定制 UI 行为，在 `index.html` 中包含了 DOM 注入与事件绑定逻辑；如果后续要长期维护，建议把这部分能力回迁到源代码工程中再重新构建。

## GitHub 发布（建议流程）

推荐把该目录作为一个独立仓库：

1. `git init`
2. 设置用户信息（例如邮箱 `xindianma@tju.edu.cn`）
3. `git add -A && git commit -m "init"`
4. 在 GitHub 创建同名仓库后配置 remote 并 `git push`

