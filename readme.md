# koishi-plugin-apexrankwatch

`koishi-plugin-apexrankwatch` 是一个用于 Koishi 的 Apex Legends 段位查询与持续监控插件。

它支持查询玩家当前段位、分数、在线状态，也支持在群聊里持续监控玩家分数变化并自动推送提醒，尽量保留旧版 Koishi 插件与 AstrBot 插件的使用体验。

## 功能特点

- 查询玩家段位、分数、等级、在线状态、当前英雄、UID
- 支持 `uid:` / `uuid:` 前缀查询
- 支持平台自动回退：`PC -> PS4 -> X1 -> SWITCH`
- 支持群聊持续监控玩家分数变化
- 支持猎杀门槛查询
- 支持当前赛季时间查询
- 支持赛季关键词自动回复与群级开关
- 兼容旧版监控数据与历史存储结构
- 对异常掉分做保护，避免 API 异常直接覆盖原始数据

## 安装

```bash
yarn add koishi-plugin-apexrankwatch
```

安装后在 Koishi 中启用插件，并填写可用的 Apex API Key 即可。

## 常用命令

- `/apextest`
- `/apexhelp`
- `/apexrank <玩家名|uid:...> [平台]`
- `/apexrankwatch <玩家名|uid:...> [平台]`
- `/apexranklist`
- `/apexrankremove <玩家名|uid:...> [平台]`
- `/apexpredator`
- `/apexseason`
- `/apexblacklist <add|remove|list|clear> <玩家ID>`
- `/赛季关闭`
- `/赛季开启`

## 命令别名

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

## 使用示例

查询玩家：

```text
/apexrank moeneri
/apexrank moeneri pc
/apexrank uid:1010153800824
```

添加群监控：

```text
/apexrankwatch moeneri
/apexrankwatch moeneri ps4
```

查看监控列表：

```text
/apexranklist
```

移除监控：

```text
/apexrankremove moeneri
```

查询赛季：

```text
/apexseason
/新赛季
```

## 使用说明

- 未指定平台时，插件会自动尝试多个平台
- 如果同名玩家存在多平台监控，移除时建议显式指定平台
- 赛季信息来自公开站点 `apexseasons.online`
- 玩家查询、监控与猎杀门槛依赖 `api.mozambiquehe.re`
- 如果没有配置可用 API Key，插件仍可加载，但在线查询类功能不可用

## 数据目录

默认数据目录为：

```text
./data/apexrankwatch
```

主要文件包括：

- `groups.json`：群监控数据
- `settings.json`：动态黑名单与赛季关键词开关

## 许可证

MIT
