# add-tweaks-claude

一个 Claude Code / agent skill：用 OpenDesign / Claude Design 的完整方式，给设计稿加上 **Tweaks 面板**。

A Claude Code / agent skill for adding a full **Tweaks panel** to a design, the OpenDesign / Claude Design way.

---

## 中文

### 它做什么
把一个设计做成多文件项目：所有视觉设置（强调色、字号比例、密度、明暗、动效、设备宽度……）都写成 `:root` 上的 CSS 变量，由 `tweaks.js` 里的 `KNOBS` 数组驱动。你改一个控件，页面立即用 `setProperty` 更新，不需要重写代码。

包含：
- `KNOBS` 数组定义所有可调项
- `localStorage` 按设计 ID 持久化，首屏就恢复
- 快捷键：`T` 开关面板，`R` 重置
- 桌面端侧边面板，手机端底部抽屉
- 顶部工具栏的 Tweaks 开关按钮
- `DESIGN.md` 设计系统文档 + `tokens.css`

只需要一个循环切换 3 个值的小芯片？用更轻的 `add-tweaks-simple`。

### 安装
```bash
git clone https://github.com/liush2yuxjtu/add-tweaks-claude.git
mkdir -p ~/.claude/skills
cp -r add-tweaks-claude/add-tweaks-claude ~/.claude/skills/
```
其他支持 `SKILL.md` 的 agent（Codex、pi 等）放到各自的 skills 目录即可。

### 用法示例
在 Claude Code 里直接说：
- 「用 add-tweaks-claude 给这个 dashboard 加 Tweaks 面板，要能调强调色、密度和明暗模式」
- 「把 landing.html 改成带 Tweaks 的多文件设计项目，再写一份 DESIGN.md」
- 「给这个设计加一个 device 旋钮，在桌面和手机宽度之间切换」

---

## English

### What it does
Turns a design into a multi-file project where every visual setting (accent, type scale, density, light/dark, motion, device width…) is a CSS custom property on `:root`, driven by a `KNOBS` array in `tweaks.js`. Changing a control calls `setProperty` and the design updates live, with no rewrite.

Includes:
- a `KNOBS` array defining every tweakable setting
- `localStorage` persistence keyed by design ID, restored on first paint
- shortcuts: `T` toggles the panel, `R` resets
- side panel on desktop, bottom drawer on mobile
- a Tweaks toggle in the viewer toolbar
- a `DESIGN.md` design system plus `tokens.css`

Need only one chip cycling through 3 values? Use the lighter `add-tweaks-simple`.

### Install
```bash
git clone https://github.com/liush2yuxjtu/add-tweaks-claude.git
mkdir -p ~/.claude/skills
cp -r add-tweaks-claude/add-tweaks-claude ~/.claude/skills/
```
Other agents that read `SKILL.md` (Codex, pi, …) can use the same folder in their skills directory.

### Usage examples
In Claude Code, just ask:
- "Use add-tweaks-claude to add a Tweaks panel to this dashboard with accent, density and light/dark knobs."
- "Turn landing.html into a multi-file design project with Tweaks and a DESIGN.md."
- "Add a device knob that switches the preview between desktop and phone width."

## Credits & License
Pattern adapted from [OpenDesign](https://github.com/nexu-io/open-design) (Apache-2.0). This repo is licensed under Apache-2.0; see `LICENSE` and `NOTICE`.
