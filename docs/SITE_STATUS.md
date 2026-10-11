# 站点配置状态

此表对应用户此前提供的五个站点。匹配依据为 `site_config/sites/*.json` 中的公开文件名和顶层站点标识；未对站点进行在线验证。

| 站点 | 配置 | 状态 |
|---|---|---|
| HDHome | `hd_home.json` | 配置存在，待验证 |
| HDU | `hdu.json` | 配置存在，待验证 |
| HDArea | `hd_area.json` | 配置存在，待验证 |
| OpenCD | `open_cd.json` | 配置存在，待验证 |
| HDTime | `hd_time.json` | 配置存在，待验证 |

## 状态说明

- **配置存在，待验证**：找到匹配的公开 JSON 配置，尚未验证其当前功能。
- **待新增配置**：站点清单中有该站点，但仓库中未找到匹配的公开 JSON 配置。

新增站点时同步更新 `MY_SITES.md`。只维护公开配置和结构信息，不连接个人 Media Saber 数据库。
