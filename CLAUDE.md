# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## 项目概述

九个自包含的 HTML 文件组成的教育演示项目，讲解 Python 基础语法。每个文件均包含内联 CSS 和原生 JavaScript，无外部依赖、无需构建工具或测试框架。

## 常用命令

- **查看**：直接在浏览器中打开任意 `.html` 文件，无需启动服务器。
- **编辑**：修改后刷新浏览器页面即可生效。

## 文件结构

- `index.html` — 首页导航，三列网格布局，按学习顺序链接到 7 个子页面。仅含静态 HTML + CSS。
- `01_input_output/index.html` — 输入输出演示：print() 多参数/格式化、input() 类型转换、缩进可视化、注释忽略过程。逐步动画 + 对话框模拟。
- `02_operator/index.html` — 运算符演示：算术计算器（7种运算网格动画）、赋值运算符（变量盒子递进动画）、比较运算符（逐项对比）、逻辑运算符（真值表+可视化）、闰年综合案例（分步条件检查）。
- `03_branch/index.html` — 分支语句演示：单分支投票检查（流程图动画）、双分支奇偶判断（分叉图+结果徽章）、多分支成绩等级（逐条件检查高亮）。
- `04_loop/index.html` — 循环演示（while + for 合并）：while 计数器/猜数字（温度条/范围可视化/撒花特效）/阶乘（进度条）；for 列表遍历（水果卡片）/累加求和/金字塔绘制。
- `05_function/index.html` — 函数演示：def 定义与调用区别、参数传递（形参→实参动画）、return 返回值（包裹传递动画）、综合案例。
- `06_string/index.html` — 字符串演示：三种表示法（单引号/双引号/三引号）、索引与切片（字符网格可视化）、基本操作（+ 拼接/* 重复/in 成员判断）、综合案例。
- `07_list/index.html` — 列表演示：创建与访问（元素网格可视化）、增删操作（append/insert/remove/pop 动画）、常用方法（extend/sort/reverse/len/count/index/in）、综合案例。
- `08_tuple/index.html` — 元组演示：创建方式（括号/无括号/单元素逗号）、索引切片可视化、不可变性（修改报错演示）、运算（+ 合并/* 重复/in/not in/len/count/index）、列表对比表、综合案例（成绩统计+元组解包）。
- `09_set/index.html` — 集合演示：创建与自动去重、四种运算（并|交&差-对称差^）、增删操作（add/discard/remove/pop/clear）、常用操作（len/in/not in/copy/set()）、包含关系（子集/超集）、数据去重应用、综合案例（班级选课系统）。
- `logo.png` — 根目录 logo 图片，被首页和所有子页面导航栏引用。

## 设计系统

- 所有页面共用同一套 CSS 自定义属性（`--bg`、`--surface`、`--surface2`、`--border`、`--text`、`--text2`、`--cyan`、`--amber`、`--green`、`--red`、`--purple`），定义在 `:root` 中。各页面独立复制，非共享 CSS 文件。
- 导航栏结构（`.navbar` > `.navbar-inner` > `.navbar-brand` + `.navbar-links`）和样式在所有子页面之间复制。修改导航需同步更新全部 6 个文件。
- 字体通过 Google Fonts 加载 `JetBrains Mono`（等宽代码字体）和 `Noto Sans SC`（正文字体），首次加载需网络连接，无离线回退。
- `index.html` 为居中全屏布局，无导航栏，使用三列网格（`grid-template-columns: repeat(3, 1fr)`）排列导航卡片；6 个子页面为顶部 sticky 导航栏 + 内容区布局。
- `.idea/` 目录为 JetBrains IDE 配置文件，`.claude/` 为 Claude Code 本地设置，均在 `.gitignore` 中排除。

## 关键模式

- 每个演示案例的 JavaScript 使用递归 `setTimeout` 实现逐步动画效果，而非 `setInterval`。
- 猜数字游戏的有效范围会随猜测动态缩小（`minGuess`/`maxGuess`），并实时显示在温度条和可选快捷按钮中。
- 导航栏通过 `.active` class 标识当前页面，各子页面各自硬编码激活状态。
- 所有子页面导航栏包含完整的 9 个链接（首页 + 8 个子页面）。

## Git 提交规范

- 提交信息使用中文，格式：`<动词> <模块>：<说明>`（如 "新增函数演示页面"、"修复输入输出页面代码展示与演示效果不匹配"）。
- 修改代码后，先**不要提交**，等待用户验证并给出提交指令后再执行 `git add` 和 `git commit`。
