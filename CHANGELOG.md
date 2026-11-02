# Changelog

## [0.3.0] - 2026-11-02

### Changed

- 展示名改为 `mem0-you`, 仓库、插件目录和 `metadata.yaml` 的 `name` 改为 `astrbot_plugin_mem0_you`.
- 版本号更新为 `0.3.0`, 同步 `metadata.yaml` 与 `main.py` 的 `@register`.
- 默认记忆索引从 `session` 改为 `sender`, 同一发送者在不同群聊和私聊中共享记忆.
- README 按自托管 mem0 重写, 补充来源、原作者和 API 兼容说明.
- 配置项与 `_conf_schema.json` 对齐, 补充 `inject_as_system_prompt` 和 `ignore_commands`.
- 移除未生效的 `mem0_api_type` 配置项, API 类型仍由 `/openapi.json` 自动探测.
- 同步更新 `AGENTS.md` 中的仓库路径、插件名和配置文件名.

### Added

- 新增本 CHANGELOG.

## [0.2.1] - 2026-10-31

### Added

- 完成自托管 mem0 OSS API 适配, 使用 `POST /memories` 和 `POST /search`.
- 启动时通过 `/openapi.json` 自动识别自托管服务, 失败时回退到官方 v3 API.
- 记忆 `user_id` 改为 `prefix:persona:session/sender` 组合, 支持按 persona 和发送者索引.
- 增加 persona 解析的多级回退逻辑, 提高获取当前人格的可靠性.

### Changed

- 写入记忆改为异步队列, mem0 请求不再阻塞 LLM 回复.
- 默认请求超时调整为 24 秒.
- 超时错误现在会带上路径和超时时间.
- 单行最大字符数放宽到 100, 并清理部分不安全写法.

## [0.2.0] - 2026-10-31

### Added

- 支持在配置中填写自托管 mem0 服务地址 `mem0_api_url_base`.

### Changed

- 更新插件版本信息和仓库链接.

## [0.1.0] - 2026-05-19

### Added

- Yuk1you 发布初始版本: 面向 mem0 官方托管 API 的 AstrBot 长期记忆插件.
