# CLAUDE.md

本文件为 Claude Code (claude.ai/code) 提供在此代码仓库中工作的指导。

## 项目概述

五个自包含的 HTML 文件组成的教育演示项目，讲解 Python 基础语法。每个文件均包含内联 CSS 和原生 JavaScript，无外部依赖、无需构建工具或测试框架。

## 常用命令

- **查看**：直接在浏览器中打开任意 `.html` 文件，无需启动服务器。
- **编辑**：修改后刷新浏览器页面即可生效。

## 文件结构

- `index.html` — 首页导航，按学习顺序链接到 4 个子页面。仅含静态 HTML + CSS。
- `01_input_output/index.html` — 输入输出演示：print() 多参数/格式化、input() 类型转换、缩进可视化、注释忽略过程。逐步动画 + 对话框模拟。
- `02_operator/index.html` — 运算符演示：算术计算器（7种运算网格动画）、赋值运算符（变量盒子递进动画）、比较运算符（逐项对比）、逻辑运算符（真值表+可视化结果）、闰年综合案例（分步条件检查）。
- `03_branch/index.html` — 分支语句演示：单分支投票检查（流程图动画）、双分支奇偶判断（分叉图+结果徽章）、多分支成绩等级（逐条件检查高亮）。结构与 while/for 对称。
- `04_loop/index.html` — 循环演示（while + for 合并）：while 计数器/猜数字（温度条/范围可视化/快捷按钮/撒花特效）/阶乘（进度条）；for 列表遍历（水果卡片）/累加求和（大数字+进度条）/金字塔绘制。

## 设计系统

- 所有页面共用同一套 CSS 自定义属性（`--bg`、`--surface`、`--surface2`、`--border`、`--text`、`--text2`、`--cyan`、`--amber`、`--green`、`--red`、`--purple`），定义在 `:root` 中。各页面独立复制，非共享 CSS 文件。
- 导航栏结构（`.navbar` > `.navbar-inner` > `.navbar-brand` + `.navbar-links`）和样式在所有子页面之间复制。修改导航需同步更新全部 5 个文件。
- 字体通过 Google Fonts 加载 `JetBrains Mono`（等宽代码字体）和 `Noto Sans SC`（正文字体），首次加载需网络连接，无离线回退。
- `index.html` 为居中全屏布局，无导航栏；4 个子页面为顶部 sticky 导航栏 + 内容区布局。
- `.idea/` 目录为 JetBrains IDE 配置文件，与项目内容无关。

## 关键模式

- 每个演示案例的 JavaScript 使用递归 `setTimeout` 实现逐步动画效果，而非 `setInterval`。
- 猜数字游戏的有效范围会随猜测动态缩小（`minGuess`/`maxGuess`），并实时显示在温度条和可选快捷按钮中。
- 导航栏通过 `.active` class 标识当前页面，各子页面各自硬编码激活状态。
- 所有子页面导航栏包含完整的 5 个链接（首页 + 4 个子页面）。
