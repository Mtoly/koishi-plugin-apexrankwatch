# koishi-plugin-apexrankwatch

Koishi 版 Apex Legends 段位查询与持续监控插件，完整兼容旧版 `koishi-plugin-apexrankwatch` 配置项，并尽量复刻 AstrBot 版插件的交互体验。

## 功能特性

- 支持查询玩家当前段位、分数、在线状态、当前英雄、UID
- 支持群聊持续监控玩家分数变化并主动推送通知
- 支持 `uid:` / `uuid:` 前缀查询
- 支持平台自动回退：`PC -> PS4 -> X1 -> SWITCH`
- 支持猎杀门槛查询
- 支持当前赛季时间查询
- 支持赛季关键词自动回复与群级开关
- 支持配置黑名单、动态黑名单、查询封禁、群白名单、用户黑名单、主人账号
- 兼容旧版 `groups.json` 数据结构与 AstrBot 风格存储字段

## 安装方式

如果你在本地 Koishi 工作区开发，直接把本插件放进工作区并启用即可。

如果你要发布或单独安装：

```bash
yarn add koishi-plugin-apexrankwatch
```

## 配置项

### 旧版 Koishi 兼容键

- `apiKey`
- `checkInterval`
- `dataDir`
- `maxRetries`
- `timeout`
- `minValidScore`
- `blacklist`

### 新版增强配置

- `debugLogging`
- `queryBlocklist`
- `userBlacklist`
- `ownerQq`
- `whitelistEnabled`
- `whitelistGroups`
- `allowPrivate`

### AstrBot 风格别名

以下 snake_case 键同样可用，会自动映射到 Koishi 配置：

- `api_key`
- `check_interval`
- `data_dir`
- `max_retries`
- `timeout_ms`
- `min_valid_score`
- `debug_logging`
- `query_blocklist`
- `user_blacklist`
- `owner_qq`
- `whitelist_enabled`
- `whitelist_groups`
- `allow_private`

## 命令说明

- `/apextest`
- `/apexhelp`
- `/apexrank <玩家|uid:...> [平台]`
- `/apexrankwatch <玩家|uid:...> [平台]`
- `/apexranklist`
- `/apexrankremove <玩家|uid:...> [平台]`
- `/apexpredator`
- `/apexseason`
- `/apexblacklist <add|remove|list|clear> <玩家ID>`
- `/赛季关闭`
- `/赛季开启`

## 别名

- `apex帮助`
- `apexrankhelp`
- `apex查询`
- `视奸`
- `apex监控`
- `持续视奸`
- `apex列表`
- `apex移除`
- `取消持续视奸`
- `apex猎杀`
- `apex赛季`
- `新赛季`
- `apex测试`
- `apex黑名单`
- `不准视奸`
- `apexban`

## 数据文件

默认数据目录为：

```text
./data/apexrankwatch
```

其中主要包含：

- `groups.json`：群监控数据
- `settings.json`：动态黑名单与赛季关键词开关

## 使用提示

- 没有配置 API Key 时，插件仍可加载，但玩家查询、监控和猎杀功能不可用
- 赛季信息来自公开站点 `apexseasons.online`
- 猎杀、玩家查询与监控依赖 `api.mozambiquehe.re`
- 如果同名玩家存在多平台监控，移除时请显式指定平台
- 插件对异常掉分做了保护：高分突然掉到极低分时会视为异常，不会直接覆盖旧分数

## 许可证

MIT
