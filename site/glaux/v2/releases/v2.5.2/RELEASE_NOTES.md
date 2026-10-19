# Glaux Translator 2.5.2

## ZH

Glaux Translator 2.5.2 是 2.5.1 的修复更新，修复窗口拖拽与章节晋升中的两个实际问题，不改变现有书籍、任务和翻译数据。

### 窗口拖拽

- 标题栏的品牌、版本号与空白区域现在共同构成深层拖拽区；从这些区域按住鼠标即可移动窗口。
- 设置按钮仍保持正常点击行为，不会被拖拽区吞掉。
- 新增标题栏交互回归测试，固定可拖拽区域与交互控件之间的边界。

### 章节晋升与出版结构

- 修复二次拆分时导航标记同时承担拆分起点与标题来源，导致 Publication Map 标题数量从预期值减少、章节无法晋升的问题。
- 拆分策略升级到 v7：导航标记与紧随其后的标题被视为不可分割结构；若该结构本身超出限制，任务会明确失败，不会悄悄删除、增加或改变标题层级。
- 恢复只重开拆分及其下游阶段，继续复用已登记的上游抽取、OCR 与可搜索 PDF 产物，不重复调用 provider，也不改写有效的前置状态。

### 验证

- 真实书籍的只读冻结副本回放已成功完成二次拆分与晋升，并证明拆分前阶段和上游产物的 attempt、artifact ID 与 SHA-256 保持不变。
- 自动化覆盖标题删除、标题新增、层级变化、超大不可分割结构以及正常晋升路径；正式发布仍经过隐私安全的 EPUB、文本 PDF 与扫描 PDF packaged gate。

## EN

Glaux Translator 2.5.2 is a corrective update to 2.5.1. It fixes two observed problems in window dragging and chapter promotion without changing existing books, jobs, or translation data.

### Window dragging

- The titlebar brand, version label, and empty space now form one deep drag region, so dragging from any of those areas moves the window.
- The Settings button remains an ordinary clickable control and is not consumed by the drag region.
- A titlebar interaction regression test now fixes the boundary between draggable surface and interactive controls.

### Chapter promotion and publication structure

- Fixes a secondary-split case where a navigation marker acted as both the split boundary and heading source, reducing the Publication Map heading count and blocking chapter promotion.
- Split policy v7 treats a navigation marker and its following heading as an indivisible structural unit. If that unit is itself oversized, the job fails explicitly instead of silently deleting, adding, or changing heading levels.
- Recovery reopens only splitting and downstream stages. Registered extraction, OCR, and searchable-PDF artifacts remain reusable, so providers are not called again and valid pre-split state is not rewritten.

### Verification

- A read-only frozen-copy replay of the affected real book completed the secondary split and promotion while preserving pre-split attempts and the artifact IDs and SHA-256 values of all upstream outputs.
- Automated coverage includes heading deletion, heading addition, level changes, oversized indivisible structures, and the successful promotion path. The formal release also runs the privacy-safe packaged gate for EPUB, text-PDF, and scanned-PDF inputs.
