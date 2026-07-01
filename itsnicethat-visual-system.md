# It's Nice That — 视觉系统参考文档

> 基于 [itsnicethat.com](https://www.itsnicethat.com) 的视觉语言系统分析
> **品牌主张** — "Inspiring Creativity"
> **目标受众** — 创意产业从业者、设计师、艺术家、文化爱好者

---

## 1. 品牌概览 Brand Overview

It's Nice That 是一个专注于创意领域的在线媒体平台，其视觉系统在**精致的简洁感**与**鲜活的个性**之间取得平衡。设计语言干净、轻盈，以大留白、高质量视觉内容为主角，紫色的品牌色作为鲜明的记忆点贯穿始终。整体调性**温暖、自信、毫不费力**。

---

## 2. 排版系统 Typography

### 2.1 字体系列 Font Families

| Token | CSS 自定义属性 | 字体 | 用途 |
|-------|---------------|------|------|
| Sans | `--sans` | **Labil**, sans-serif | 正文、标题、界面文字 |
| Sans Variable | `--sans-variable` | **LabilVariable**, Labil, sans-serif | 可变字体场景（粗细/稳定性轴） |
| Sans Alt | `--sans-alt` | **GT-Planar**, sans-serif | 大写标题、taient 卡片、导航按钮 |

### 2.2 字体特征与变量轴

**LabilVariable** 使用两个变量轴：
- `wght` (Weight): 30 = light/regular, 400 = normal, 值越大越粗
- `stbl` (Stability): 50-100 之间，影响字形的稳定感/紧凑度

出现在文章标题中：`font-variation-settings: "wght" 30, "stbl" 100`

**GT-Planar** 专为大写排版设计：
- `text-transform: uppercase`
- `letter-spacing: -0.05em`（负字距，紧凑有力）
- `line-height: 1.25`

### 2.3 字号系统 Font Sizes

使用 `clamp()` 实现流动式缩放。以下是典型字号映射：

| 用途 | CSS | 典型范围 |
|------|-----|---------|
| 文章标题 (h3) | `h3` sans | 流动，约 20-28px |
| 文章副标题 | `feed-item__body` | 20px (桌面) |
| 产品/taient 标题 | `clamp(20px, 2vw, 28px)` | 20-28px |
| 小标题 | `clamp(20px, 2.5vw, 35px)` | 20-35px |
| 导航链接 | `text-caption-40` | ~13-17px |
| 分类标签 / 按钮 | `font-size: 13px` | 固定 13px |
| 时间日期 | `text-caption-20` 或 `h6` | ~11-12px |
| 文章卡片简介 | `clamp(17px, 2vw, 20px)` | 17-20px |
| 导航按钮小字 | `font-size: 11px` | 固定 11px |

### 2.4 行高 Line Heights

| 场景 | line-height |
|------|------------|
| 正文 / 富文本 | 1.5 |
| 文章标题 | 1.3 |
| 大写标题 (GT-Planar) | 1.25 |
| 按钮小字 | 1.4 |

---

## 3. 色彩系统 Color System

### 3.1 品牌主色 Brand Colors

#### **紫色 Purple** (品牌锚点)

| Token | 值 | 用途 |
|-------|-----|------|
| `--color-brand-primary-purple-100` | **#6219FF** | 品牌色主色 |
| `--color-brand-primary-purple-80` | **#8147FF** | 次要按钮、激活态 |
| `--color-brand-primary-purple-24` | **rgba(98,25,255,.24)** | 选中高亮、悬停背景 |
| `--color-brand-primary-purple-10` | **#F9F5FF** | 纯色背景块 |
| `--color-brand-primary-purple-6` | **rgba(98,25,255,.06)** | 极淡悬停背景 |

`hsla(0,0%,40.4%,.20)` 等变体用于辅助色。

#### **黑色 Base Black**

| Token | 值 | 用途 |
|-------|-----|------|
| `--color-base-black-100` | **#2B2B2B** | 正文色、主文字 |
| `--color-base-black-80` | **rgba(43,43,43,.80)** | 次要文字 |
| `--color-base-black-64` | **rgba(43,43,43,.64)** | 占位文字、辅助信息 |

#### **灰色 Base Gray**

| Token | 值 | 用途 |
|-------|-----|------|
| `--color-base-gray-100` | **#676767** | 次要文字、来源信息 |
| `--color-base-gray-20` | **#F4F4F4** | 卡片/区域背景色 |
| `--color-base-gray-10072` | hsla(0,0%,40.4%,.72) | 辅助文字 |
| `--color-base-gray-10040` | hsla(0,0%,40.4%,.40) | 时间戳、次要信息 |
| `--color-base-gray-10020` | hsla(0,0%,40.4%,.20) | 分割线、边框 |
| `--color-base-gray-10012` | hsla(0,0%,40.4%,.12) | 极淡分割线 |
| `--color-base-gray-1008` | hsla(0,0%,40.4%,.08) | 标签背景、极淡网格 |

#### **白色 Base White**

| Token | 值 | 用途 |
|-------|-----|------|
| `--color-base-white-100` | **#FFFFFF** | 白色文字/背景 |
| `--color-base-white-10012` | hsla(0,0%,100%,.12) | 深色背景上的分隔线 |

#### **补充色 Legacy Colors**

| 名称 | 值 |
|------|-----|
| Dark Grey | `#222` |
| Grey | `#555` |
| Light Grey | `#e8e8e8` |
| Blue | `"blue"` (占位) |
| Green | `"green"` (占位) |
| Orange | `"orange"` (占位) |
| Red | `"red"` (占位) |
| Yellow | `#FFD519` (按钮/强调) |

### 3.2 色彩使用原则

- 主内容区文字始终使用 `#2B2B2B`（base-black-100）
- 辅助信息使用 `#676767`（gray-100）
- 时间戳使用 40% 不透明度的灰色
- 品牌紫色主要用于：链接悬停态、分类标签、按钮激活态、高亮背景
- 卡片底纹、浅色背景使用 `#F4F4F4`
- 产品/商店卡片使用微妙紫色背景 `rgba(174,160,204,.2)`

---

## 4. 间距系统 Spacing System

### 4.1 间距 Token

| Token | CSS 自定义属性 | 值 |
|-------|---------------|-----|
| Space 1 | `--space-1` | **1px** |
| Space 2 | `--space-2` | **1rem** (16px) |
| Space 3 | `--space-3` | **2rem** (36px) |
| Space 4 | `--space-4` | **4rem** (72px) |
| Space 5 | `--space-5` | **5rem** (80px) |
| Space 6 | `--space-6` | **6rem** (96px) |
| Space 7 | `--space-7` | **7rem** |
| Space 8 | `--space-8` | **8rem** |

### 4.2 Gap 系统

| 值 | 用途 |
|----|------|
| **1px** | 列表/网格项目之间的细分隔线 |
| **8px** | 内联元素间距、图标与文字间距 |
| **16px** | 卡片内间距、导航间隙 |
| **24px** | 较大块间距、网格间距 |
| **40px** | 大区间距、分节间距 |
| **80px** | 页面中超大间距 |

---

## 5. 布局系统 Layout

### 5.1 容器与断点

| 名称 | CSS 自定义属性 | 值 |
|------|---------------|-----|
| Container 宽 | `--container-width` | **1440px** |
| 桌面大屏 (lg) | `min-width: 1480px` | 超大布局 |
| 桌面中屏 (md) | `min-width: 1080px` | 标准桌面 |
| 平板 (sm) | `min-width: 768px` | 平板 |
| 手机 | `max-width: 767px` | 移动端 |

### 5.2 网格系统 Grid System

采用 12 列的浮动浮点网格系统，百分比宽度：

| 列数 | 宽度 |
|------|------|
| col-3 | 25% |
| col-4 | 33.33% |
| col-6 | 50% |
| col-12 | 100% |

响应式前缀：`sm-`, `md-`, `lg-` 用于不同断点。

### 5.3 容器层级

```
.container (max-width: 1440px, margin: 0 auto)
  └── .container-gutter (带内边距版本)
```

关键最大宽度预设：
- `--width-1`: 24rem
- `--width-2`: 32rem
- `--width-3`: 48rem
- `--width-4`: 64rem

---

## 6. UI 组件系统 Components

### 6.1 导航 Navigation

**顶部导航栏 (Masthead)**
- 高度: 64px (桌面) / 48px (手机)
- 链接间距: `gap: 1px`（细分隔线）
- 背景色: `#FFEDD1`（暖米色）
- 链接小图标: 16x16px 圆形容器，10% 透明背景
- 文字大小: 11px

**底部浮动导航 (Nav Bar)**
- **形状**: 胶囊形 (border-radius: 75px)
- **背景**: `hsla(0,0%,95.7%,.64)` + `backdrop-filter: blur(32px)`
- **阴影**: 多层柔和阴影 `0 24px 38px 0 rgba(0,0,0,.08)` 等
- **高度**: 48px (手机) / 57px (桌面)
- **Logo**: 圆形，同样 75px 圆角，额外 backdrop-filter: blur(3px)
- **位置**: 固定到底部，bottom: 16-32px，左右 16px
- **内部按钮**: 紫色填充 `bg-violet`，pill 形状

### 6.2 文章卡片 Article Cards

**结构**
```
.listing-item
  ├── 图片区域 (aspect-ratio 可变: 56.25%, 100%, 125%, 141%...)
  │   └── 背景色占位 (2秒淡入过渡)
  ├── 标题 (h3.sans, variable font)
  └── 日期 (h6.sans, 灰色)
```

**视觉特征**
- 白色卡片背景，无边框（靠间距形成分割）
- 图片宽高比多样化：16:9, 1:1, 4:3, 3:2, 3:4 等
- 标题使用可变字体粗细 `wght: 30`
- 日期与标题之间有 `margin-top: 3` 间距
- 内边距: 上下 16px (py4)，左右 16-24px (px4/px3)
- 标签位于卡片底部

### 6.3 分类标签 Tags / Magnolia

```
.magnolia.tag
  ├── 紫色文字 (h6.sans.purple)
  └── 半透明背景 (--color-base-gray-1008)
```

**特征**
- 紧凑: `padding: 5.5px 9px`
- `gap: 1px` 标签间细线分隔
- 悬停 "..." 显示更多标签

### 6.4 按钮 Buttons

| 类型 | 样式 | 圆角 | 状态 |
|------|------|------|------|
| 常规按钮 | `btn`, 带边框 | 无 | hover-darken |
| 探索按钮 | 紫色填充 + 白色文字 | 75px (pill) | hover 变深 |
| 搜索按钮 | 紫色填充 | 75px | 居中图标+文字 |
| 商店链接 | `#8147FF` 填充 | 100px | hover → `#6219FF` |
| 标签/筛选项 | 灰色背景 `#F4F4F4` | 0 → hover 40px | active: 紫色24% |
| Talent 按钮 | 黑色填充 | 0 | 仅移动端显示 |
| 查询提交按钮 | `color: #FFD519`(黄色文字) | 无 | hover 变暗 |

### 6.5 信息卡片 Talent/Product Cards

**Talent Card**
- 内边距: `16px 16px 8px`
- 悬停渐变覆盖: `linear-gradient(180deg, #ed4870, #de8dff 53.85%, #e5d6f6)`
- 标题: GT-Planar, uppercase, `clamp(20px,2vw,22px)`, letter-spacing: -0.05em
- 分隔线: 顶部 1px solid `--color-base-gray-10020`
- 标签圆角: 无 (0)

**Product Card**
- 背景: `rgba(174,160,204,.2)` (淡紫色)
- 标题: LabilVariable, `clamp(20px,2vw,28px)`
- 来源行: `opacity: .56` 半透明
- 分隔线: 虚线效果 `linear-gradient(90deg,#000 25%,transparent 0)` repeat-x
- 悬停覆盖: 纯紫色 `rgba(98,25,255,.24)`

### 6.6 Feed Preview 水平预览条

- 头部背景: `#F4F4F4`
- 标题: 内联 flex, gap 8px
- 滑动手势: 左右滑动
- 缩略图: `aspect-ratio: 120/109`
- 悬停: 背景变紫色 6%，标题变紫色 100%

### 6.7 分类导航 Discipline/Category Nav

**特征**
- 水平/换行排列，`gap: 1px` (talent) 或 `gap: 4px` (product)
- 滚动: 溢出隐藏，无滚动条
- 按钮: 灰色背景 `#F4F4F4`，无圆角，hover 到 40px 圆角
- 激活态: 紫色背景 24% (talent) 或紫色填充 80% (product)
- 过渡: `cubic-bezier(.19,1,.22,1)` 弹性动画

### 6.8 Newsletter 组件

- 背景: `#2B2B2B` (黑色)
- 标题: 可变字体, `wght: 30, stbl: 50`
- 输入框: 无边框，白色文字
- 按钮: 黄色文字 `#FFD519`，深色背景
- 内边距: 大量留白 (px5/px6)

### 6.9 页脚 Footer

- 背景: `mineshaft` (深色)
- 顶部边框: 1px solid `dove-grey`
- 5 列网格布局: 每个列宽 `10-2` (约 20%)
- 文字: white + dove-grey
- 行高: line-height-3 (宽松)

---

## 7. 设计模式与交互 Design Patterns

### 7.1 悬停效果 Hover States

| 场景 | 效果 | 过渡 |
|------|------|------|
| 文章卡片悬停 | 无变化（图片本身可点击） | — |
| Feed slide 悬停 | 背景变紫色 6%，标题变紫色 100% | `.3s ease` |
| Tag/分类按钮悬停 | `border-radius: 40px` 平滑展开 | `.3s cubic-bezier` |
| Talent 卡片悬停 | 渐变覆盖 fade in (粉色→紫色→淡紫) | `.6s ease-out` |
| Product 卡片悬停 | 紫色覆盖 fade in | `.6s ease-out` |
| Talent header 按钮 | 背景变深灰色 | `.3s ease` |
| 商店链接悬停 | 紫色 80% → 紫色 100% | `.3s ease` |

### 7.2 边框与分割

- **1px** 是核心分割单位：grid gap:1px 创造极细边框效果
- 卡片无边框，通过背景色对比 + 间距实现视觉分隔
- 列表项之间使用 `1px solid --color-base-gray-10020` 半透明分割线

### 7.3 图片处理

- 最大宽度 100%（`img { max-width: 100% }`）
- 使用 `aspect-ratio` + padding-bottom 技术保持比例
- 图片加载前有背景色占位（2秒 `transition: opacity 2s`）
- 宽高比预设: 1:1, 2:1, 3:1, 3:2, 4:3, 16:9, 375:480

### 7.4 阴影系统

导航阴影层级:
```
box-shadow:
  0 -11px 15px 0 rgba(0,0,0,.08),
  0 24px 38px 0 rgba(0,0,0,.08),
  0 9px 46px 0 rgba(0,0,0,.08),
  0 11px 15px 0 rgba(0,0,0,.08)
```

### 7.5 毛玻璃效果

```
-webkit-backdrop-filter: blur(32px);
backdrop-filter: blur(32px);
```

用于底部浮动导航栏，在彩色/图片背景上产生细腻磨砂玻璃效果。

### 7.6 图标系统

- 使用内联 SVG 图标
- 名称命名: `.icon-smile`, `.icon-search`, `.icon-burger`, `.icon-logo`
- Logo: 自定义 SVG 笑脸标志 + "It's Nice That" 文字标志

---

## 8. 页面结构模板 Page Architecture

### 8.1 主页 Homepage

```
.masthead-header (横幅广告区)
.nav-bar (浮动导航，fixed 到底部)
.masthead-links (品牌合作链接行)
.container (主内容)
  ├── Logo 区域
  ├── Categories (标签云)
  ├── Articles Grid (文章网格)
  │   └── .listing-item × N
  ├── Advert 模块
  ├── Newsletter 模块
  └── Footer
```

### 8.2 文章详情 Article Detail

```
.header (含分类、元数据)
  ├── 标题
  ├── 日期/作者
  └── 分享按钮
.module-banner (主图)
.module-content (富文本正文)
  └── .rich-text
.module-related (相关推荐)
```

### 8.3 Talent / Product 详情

```
.talent-header (返回按钮 + logo)
.talent-container
  ├── .talent-info (sticky 侧边栏)
  │   ├── 标题
  │   ├── 简介信息
  │   └── 商店/社交媒体链接
  └── .talent-gallery (作品集画廊)
       └── .talent-gallery__items (竖向排列)
```

---

## 9. 设计原则总结 Design Principles

1. **内容为王** — 大量留白让视觉作品本身成为主角，UI 退居幕后
2. **紫色锚定** — 品牌紫色是唯一的强调色，使用克制但有力
3. **1px 分隔** — 微米级分割线构成网格节奏，替代传统卡片边框
4. **流动式排版** — `clamp()` 函数让文字在任何视口都自然缩放
5. **卡片无框化** — 卡片无边框/无阴影，靠间距和背景色区分层级
6. **磨砂导航** — 毛玻璃导航提供功能性同时保持视觉轻盈
7. **优雅的悬停** — 悬停态多用半透明覆盖、紫色 tint、圆角变化，避免生硬
8. **双字体系统** — Labil 做干净正文 + GT-Planar 做大写标题形成对比
9. **深色页脚** — 深色底收束页面，与白色内容形成鲜明对照
10. **一致的过渡** — 几乎所有交互使用 `0.3s ease`，形成统一的交互节奏

---

## 10. 设计标签 Design Tokens (CSS 自定义属性汇总)

```css
:root {
  /* Colors */
  --color-brand-primary-purple-100: #6219FF;
  --color-brand-primary-purple-80:  #8147FF;
  --color-brand-primary-purple-24:  rgba(98,25,255,.24);
  --color-brand-primary-purple-10:  #F9F5FF;
  --color-brand-primary-purple-6:   rgba(98,25,255,.06);
  --color-base-black-100: #2B2B2B;
  --color-base-black-80:  rgba(43,43,43,.80);
  --color-base-black-64:  rgba(43,43,43,.64);
  --color-base-gray-100:  #676767;
  --color-base-gray-20:   #F4F4F4;
  --color-base-white-100: #FFFFFF;

  /* Typography */
  --sans:         Labil, sans-serif;
  --sans-variable: LabilVariable, Labil, sans-serif;
  --sans-alt:     GT-Planar, sans-serif;

  /* Spacing */
  --space-1: 1px;
  --space-2: 1rem;
  --space-3: 2rem;
  --space-4: 4rem;
  --space-5: 5rem;
  --space-6: 6rem;
  --space-7: 7rem;
  --space-8: 8rem;

  /* Layout */
  --container-width: 1440px;
  --border-width: 1px;
  --muted: 0.4;

  /* Legacy */
  --dark-grey:  #222;
  --grey:       #555;
  --light-grey: #e8e8e8;
}
```

---

> 文档生成日期: 2026-06-29
> 分析来源: [itsnicethat.com](https://www.itsnicethat.com) CSS 与 HTML 源码
