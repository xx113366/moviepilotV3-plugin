# MoviePilot V3 插件聚合库

这是一个面向 MoviePilot V3 的第三方插件聚合仓库，当前包含绿联社区签到和磁盘清理两个插件。仓库采用 MoviePilot V3 的插件市场清单格式，各插件位于独立目录，安装一个插件不会覆盖其他插件。

## 在 MoviePilot 中添加

在 MoviePilot V3 的插件市场中选择“添加第三方仓库”，填写本仓库地址。

```text
https://github.com/xx113366/moviepilotV3-plugin
```

刷新插件列表后，按名称搜索并安装需要的插件。仓库清单位于 [`package.v3.json`](package.v3.json)。

## 插件列表

| 插件 | 目录 | 主要用途 | 说明 |
| --- | --- | --- | --- |
| 绿联论坛签到 | [`plugins.v3/ugreendiscuz`](plugins.v3/ugreendiscuz) | 自动完成绿联社区每日签到 | 需要在 MoviePilot 配置 Cookie |
| 磁盘清理 | [`plugins.v3/diskcleaner`](plugins.v3/diskcleaner) | 按空间、做种时长和整理记录清理本地数据 | 首次使用建议开启演练模式 |

## 磁盘清理

磁盘清理插件支持三种处理流程。

- 媒体优先。媒体库空间不足时，按媒体老化顺序处理媒体目录。
- 下载器优先。下载目录空间不足或做种超过设置时长时，按下载器任务处理。
- 整理记录优先。按 MoviePilot 整理记录从旧到新处理媒体、刮削文件、做种和历史记录。

整理记录优先流程提供两种触发方式。

- 命中空间或做种阈值时处理，适合只在需要释放空间时运行。
- 每次计划执行都检查最旧记录，适合持续整理长期积累的历史记录。该模式仍受冷却时间和容量上限限制。

### 推荐配置顺序

1. 开启演练模式，确认日志中的清理目标和目录范围。
2. 选择触发流程和清理范围相关的删除动作。
3. 设置近期整理记录保护天数，建议先保留 30 天。
4. 确认单轮条目数、单轮释放容量和每日释放容量。
5. 确认无误后关闭演练模式，再执行真实清理。

清理目录来自 MoviePilot 配置的本地媒体库目录。配置页面会显示当前识别到的目录。媒体服务器和媒体库多选项用于清理后的刷新目标，路径映射用于容器内外路径不一致的情况。

完整配置和流程说明见 [`plugins.v3/diskcleaner/USAGE.md`](plugins.v3/diskcleaner/USAGE.md)。

## 绿联社区签到

绿联论坛签到插件支持每日自动签到、签到状态确认、连续签到天数展示，以及 Cookie 失效时的登录备用流程。安装后在 MoviePilot 插件配置中填写 Cookie。

原始项目和插件地址见 [madrays/MoviePilot-Plugins](https://github.com/madrays/MoviePilot-Plugins)。

## 来源与许可

本仓库保留各插件的原作者和来源信息。

- 绿联社区签到来源于 [madrays/MoviePilot-Plugins](https://github.com/madrays/MoviePilot-Plugins)。
- 磁盘清理来源于 [baozaodetudou/MoviePilot-Plugins](https://github.com/baozaodetudou/MoviePilot-Plugins)。
- 仓库按 AGPL-3.0-only 发布，详见 [`LICENSE`](LICENSE) 和 [`NOTICE`](NOTICE)。

请勿把 Cookie、密码、API Token 或其他凭据提交到仓库。
