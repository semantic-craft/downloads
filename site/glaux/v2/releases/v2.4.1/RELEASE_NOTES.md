# Glaux Translator 2.4.1

## ZH

这是一个针对扫描书中文原书成书流程的修复版本。

- 修复 OCR 已成功生成 normalized OCR 文档，但 Launcher 注册 `normalized_ocr` artifact 时漏掉契约版本、来源哈希、页数和区块数等证据，导致中文原书同语言交接报错的问题。
- 修复同时适用于只生成 normalized OCR 的流程，以及连同原页 PDF（可选字）一起生成的流程；交接现在会继续生成结构化 Markdown，并把对应证据写入书籍工程的 source manifest。
- 更新通道迁移到 Responsay 的 Cloudflare R2。2.4.0 客户端会通过一次性旧通道 bridge 获得 2.4.1；从 2.4.1 开始，后续更新直接读取永久 R2 通道，不再依赖旧 ECS 发布链路。
- 本版本的完整对应源码与二进制产物一同按版本固定发布，并提供 SHA-256 校验文件。

本版本仍只支持 macOS Apple Silicon。App 与 DMG 均使用 Developer ID 签名、经 Apple 公证并 staple；应用内更新包另有独立签名。

## EN

This patch fixes the scanned-book same-language publication handoff.

- OCR could successfully produce a normalized OCR document while the Launcher omitted its contract version, source hash, page count, and block count when registering the `normalized_ocr` artifact. The Chinese same-language handoff then failed despite completed OCR. Those evidence bindings are now preserved.
- The fix covers both normalized-only output and scans that also produce a searchable original-page PDF. Handoff continues into structured Markdown and records the bound evidence in the book project's source manifest.
- The update channel moves to Responsay's Cloudflare R2 distribution. Version 2.4.0 receives 2.4.1 through a one-time legacy bridge; 2.4.1 and later read the permanent R2 channel directly instead of depending on the former ECS publication path.
- Complete corresponding source is published immutably beside this version's binary artifacts, with a SHA-256 checksum file.

This release remains macOS Apple Silicon only. The App and DMG are Developer ID signed, Apple notarized, and stapled; the in-app updater bundle carries its separate update signature.
