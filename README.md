# LogX - 高性能 Web 日志威胁分析工具

<p align="center">
  <img src="build/appicon.png" alt="LogX Logo" width="120">
</p>

<p align="center">
  <strong>🚀 基于 Go + Wails + Vue 3 的现代化日志分析与威胁检测平台</strong>
</p>

<p align="center">
  <a href="https://github.com/AakiTT/LogX">
    <img src="https://img.shields.io/github/stars/AakiTT/LogX?style=flat-square&color=blue" alt="GitHub Stars">
  </a>
  <a href="https://github.com/AakiTT/LogX/forks">
    <img src="https://img.shields.io/github/forks/AakiTT/LogX?style=flat-square&color=green" alt="GitHub Forks">
  </a>
  <a href="https://github.com/AakiTT/LogX/issues">
    <img src="https://img.shields.io/github/issues/AakiTT/LogX?style=flat-square&color=orange" alt="GitHub Issues">
  </a>
  <a href="https://github.com/AakiTT/LogX/releases">
    <img src="https://img.shields.io/github/v/release/AakiTT/LogX?style=flat-square&color=purple" alt="GitHub Release">
  </a>
</p>

<p align="center">
  <a href="#特性">特性</a> •
  <a href="#安装">安装</a> •
  <a href="#使用">使用</a> •
  <a href="#开发">开发</a> •
  <a href="#技术栈">技术栈</a> •
  <a href="#更新日志">更新日志</a>
</p>

---

## ✨ 项目简介

**LogX** 是一款专为应急响应、安全分析和攻防演练设计的现代化桌面应用。它结合了 Go 语言的高性能并发解析能力与 Vue 3 的交互式可视化体验，能够快速处理百万级 Web 日志，自动识别 SQL 注入、XSS、WebShell、暴力破解等常见攻击，并提供直观的攻击溯源、会话关联和地理定位功能。

---

## 🔥 核心特性

### 🔍 极速日志解析
- **多格式支持**：自动识别 Apache、Nginx、IIS、JSON、CLF 等常见日志格式，并支持通用格式兜底解析。
- **高性能引擎**：基于 Go 并发处理与流式写入 SQLite，秒级解析百万条日志记录。
- **自定义格式**：支持正则表达式自定义解析规则，适应各种非标日志与业务日志。

### 🛡️ 智能威胁检测
内置丰富的检测规则库，自动识别各类 Web 攻击：
- **高危攻击**：SQL 注入、XSS 跨站脚本、命令执行 (RCE)、文件包含、反序列化。
- **WebShell**：自动检测菜刀、蚁剑、冰蝎、哥斯拉等连接特征。
- **扫描器识别**：识别 Nmap、SQLMap、DirBuster、OpenVAS 等扫描器指纹。
- **漏洞利用**：Log4j2、Fastjson、Struts2、ThinkPHP、WebLogic 等常见漏洞利用尝试。
- **暴力破解**：基于频率统计自动识别登录爆破行为。
- **AI 辅助**：集成 AI 助手，对疑难日志进行深度分析、解释与处置建议。

### 📊 可视化分析
- **攻击大屏**：实时展示攻击态势、威胁等级分布、Top 攻击源与请求路径。
- **路径分析树**：独创的树状视图，快速梳理网站目录结构和访问热度。
- **地理溯源**：基于 ECharts 的 2D/3D 地球视图，精准定位攻击者物理位置。
- **攻击会话**：自动关联同一攻击者的完整会话轨迹，还原攻击路径。
- **交互式图表**：支持多维度的流量趋势、状态码分布和请求方法分析。

### ⚡ 高效交互体验
- **透明标题栏**：自定义无边框窗口，顶部标题栏完全透明，沉浸式深色界面。
- **多维过滤**：支持 IP、时间范围、HTTP 方法、状态码、威胁等级、攻击类型组合筛选。
- **虚拟滚动**：流畅浏览海量日志数据，无卡顿。
- **一键导出**：威胁日志支持导出为 XLSX，便于报表与溯源。

---

## 🚀 使用指南

### 1. 导入日志
- 点击顶部 **导入** 按钮，选择单个文件、多个文件或整个日志目录。
- 支持 `.log`、`.txt`、`.access`、`.error` 等常见后缀。

### 2. 威胁检测
- 进入 **威胁检测** 模块，点击 **Run Detection** 扫描所有日志。
- 支持按威胁等级、时间范围、状态码等维度筛选威胁日志。
- 点击单条威胁可查看原始日志、攻击载荷和攻击标签详情。

### 3. 攻击分析
- 进入 **攻击分析** 模块，查看 DDoS 检测、扫描器识别、攻击类型分布和攻击时间线。

### 4. 地理定位
- 在 **地理分析** 模块查看攻击源全球分布。
- 支持 2D/3D 模式切换，直观展示攻击热点区域。

### 5. 规则管理
- 在 **规则管理** 中自定义正则匹配规则，扩展检测能力。

---

## 🛠️ 技术栈

- **后端**：Go 1.21+、Wails v2、SQLite、ip2region
- **前端**：Vue 3、Vite、Pinia、TailwindCSS
- **可视化**：ECharts 5、ECharts-GL
- **构建**：Wails CLI

---

## 📸 界面预览

<p align="center">
  <img src="docs/screenshot-dashboard.png" alt="仪表盘" width="80%">
  <br>
  <em>仪表盘 - 全局攻击态势一览</em>
</p>

<p align="center">
  <img src="docs/screenshot-threat.png" alt="威胁检测" width="80%">
  <br>
  <em>威胁检测 - 多维度筛选与详情</em>
</p>

---


## 📄 许可证

本项目采用 [MIT](LICENSE) 许可证。

---

<p align="center">
  <strong>LogX</strong> 由 <a href="https://github.com/AakiTT">AakiTT</a> 开发维护
</p>
