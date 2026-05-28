# ZMK Config for Crosses/Bridges

![ZMK 构建状态](https://img.shields.io/github/actions/workflow/status/HeeTuic/zmk-for-crosses/build.yml?branch=35&label=ZMK%20Build&style=for-the-badge&color=2ac3de) ![键盘映射图绘制](https://img.shields.io/github/actions/workflow/status/HeeTuic/zmk-for-crosses/draw-keymaps.yml?label=Keymap%20Draw&style=for-the-badge&color=bb9af7) &nbsp;&nbsp;&nbsp;&nbsp; [![English](https://img.shields.io/badge/%F0%9F%8C%90%20Language-English-1b4c7e?style=for-the-badge)](README.md)[![简体中文](https://img.shields.io/badge/-%20%E7%AE%80%E4%BD%93%E4%B8%AD%E6%96%87-2e6b5e?style=for-the-badge)](README_ZH.md)

本仓库为 **“喵喵喵猫”硬件改版**的 Crosses/Bridges 分体键盘提供了官方 ZMK 固件。它原生支持通过 ZMK Studio 进行实时改键，并深度优化了无线连接与功耗。

### 该分支适用于 3x5 配列单手轨迹球变体。
- 3x5 配列双轨迹球无线版本，请使用此库：[zmk-for-crosses35-dual](https://github.com/HeeTuic/zmk-for-crosses35-dual)  
- 3x6 配列双轨迹球无线版本，请使用此库：[zmk-for-crosses36-dual](https://github.com/HeeTuic/zmk-for-crosses36-dual)  
- 4x6 配列双轨迹球无线版本，请使用此库：[zmk-for-crosses46-dual](https://github.com/HeeTuic/zmk-for-crosses46-dual)  

---

## 🗺️ 键盘布局图 (Keymap Layout)

![Crosses 键盘布局](img/crosses.svg)

*每当对 `.keymap` 文件提交更改时，此布局图都会通过 GitHub Actions 自动生成并更新。*

---

## 🛠️ 图形化配置

### 1. ZMK Studio（简单的实时改键）
无需重新刷写固件，即可利用官方 ZMK Studio 协议随时随地修改你的键位，所有更改立即生效。
- **如何使用**：使用兼容的 Chromium 内核浏览器（如 Chrome 或 Edge）打开并连接到 [ZMK Studio](https://zmk.studio/)，或者使用独立安装的桌面客户端。
- **核心优势**：**即时通讯**。通过 USB (WebHID) 或网页蓝牙直接与硬件交互。这省去了等待 GitHub Actions 编译或手动刷写固件的过程，非常适合对基础键位进行日常的快速微调。

### 2. Keymap Editor（在线全功能编译）
社区中最成熟的视觉网页编辑器，与你的 GitHub 工作流深度集成。非常适合对你的键盘布局架构进行全面的调整。
- **如何使用**：[Fork](https://docs.github.com/en/get-started/quickstart/fork-a-repo#forking-a-repository) 本仓库，并在 [GitHub Actions](https://docs.github.com/en/actions/managing-workflow-runs-and-deployments/managing-workflow-runs/disabling-and-enabling-a-workflow#enabling-a-workflow) 标签页下运行初始的固件编译。然后登录 [Keymap Editor](https://nickcoutsos.github.io/keymap-editor/)，授权访问并选择你的 `zmk-for-crosses` 仓库。
- **核心优势**：**全功能编辑**。在直观的图形界面中通过拖放来修改键位，完美支持组合键 (Combos)、宏 (Macros) 以及高级 ZMK 行为 (Behaviors)。保存更改会自动将代码提交到 GitHub 并触发云端构建。

---

## 🚀 固件刷写指南

> **📌 刷写须知：**
> - **需要刷写**：只有在通过 **Keymap Editor** 修改布局、直接编辑**仓库源代码**或对新键盘进行**初始设置**时，才需要执行以下刷写步骤。
> - **无需刷写**：如果你使用 **ZMK Studio** 进行实时键位调整，更改会直接保存到硬件的板载闪存中。你可以完全跳过本指南。

### 标准刷写工作流：

1. **固件编译**：在 Keymap Editor 中保存更改或推送代码提交将自动触发 GitHub Actions 构建。前往你仓库的 **Actions** 标签页查看最新的构建状态。
2. **下载固件**：构建成功完成后，滚动到构建页面底部的 **Artifacts（产物）** 区域，下载 `firmware.zip`。
3. **解压文件**：解压压缩包，获取对应键盘左右两半的 `left.uf2` 和 `right.uf2` 固件文件。
4. **触发引导模式 (Bootloader)**：使用 USB 数据线将键盘的一半连接到电脑。双击控制器上的硬件复位 (Reset) 按钮进入引导模式（设备将作为虚拟海量存储盘挂载到你的电脑上）。
5. **刷入固件**：将对应的 `.uf2` 文件拖放到该虚拟磁盘中。微控制器会自动刷入固件、重启并自动弹出磁盘。

> **⚠️ 注意：** 键盘左半部分和右半部分的微控制器是独立运行的。你必须分别通过 USB 连接并刷写每一半。

---

## 📝 致谢与支持

*   **文档说明**：本篇文档在 AI 的协助下起草，并由作者进行了严格的审查与润色，以确保技术准确性。对于自动化可能导致的任何轻微语言习惯差异或生硬表述，我们深表歉意。
*   **技术支持**：如果你在使用 Crosses/Bridges 分体键盘时遇到任何关于固件使用、图形化配置或刷写的问题，欢迎通过以下渠道联系作者：
    *   **📩 Gmail**: `heetuic@gmail.com`
    *   **🐟 闲鱼**: 搜索用户 **"喵喵喵猫"**

---
