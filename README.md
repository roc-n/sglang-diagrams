# sglang-diagrams

SGLang 源码分析系列的可视化图表（单文件、可交互的 HTML）。

## 内容

| 文件 | 图 | 说明 |
| :--- | :--- | :--- |
| [`index.html`](index.html) | SGLang 请求生命周期全景：三条流，一张图 | 对应《SGLang 请求生命周期与 Prefill / Decode 源码分析》第 1.1 节，泳道图：客户端 → 主进程（HTTP Server + TokenizerManager）→ Scheduler 子进程（每 rank 一个）→ Detokenizer 进程，控制流 ① → ⑨ |

图由 [Archify](https://github.com/tt-a1i/archify) 生成，自包含单文件（字体与图标已内嵌，无外部依赖），支持：

- 深色 / 浅色主题切换
- 路径高亮、逐节点聚焦
- 右上角「导出」为 PNG / SVG / WebP

## 源码基线

图中节点的来源链接指向：

```
sgl-project/sglang @ 3ed56a341b57eb57c8e37e0cec353e67ebb35c3b (2026-09-25)
```

## 在线访问

开启 GitHub Pages 后访问：

```
https://roc-n.github.io/sglang-diagrams/
```

> 注意：请直接从 Pages 地址访问。`raw.githubusercontent.com` 的链接返回 `text/plain` 并带 CSP sandbox，浏览器只会显示源码，图形与交互不会生效。

## 更新图

```bash
# 用新导出的 HTML 覆盖 index.html 后
git add index.html
git commit -m "Update diagram"
git push
```

Pages 会在推送后自动重建。
