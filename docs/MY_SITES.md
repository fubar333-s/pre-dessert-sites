# 我的站点清单

站点列表依据用户此前提供的站点名称及截图整理。配置匹配只检查 `site_config/sites/*.json` 的文件名及公开顶层 `id`、`code`、`name`；能力项只记录对应请求项是否存在，不读取请求内容或私人数据。

| 站点名称 | site_code | 配置文件 | 配置状态 |
|---|---|---|---|
| HDHome | `hd_home` | `hd_home.json` | 配置存在，待验证 |
| HDU | `hdu` | `hdu.json` | 配置存在，待验证 |
| HDArea | `hd_area` | `hd_area.json` | 配置存在，待验证 |
| OpenCD | `open_cd` | `open_cd.json` | 配置存在，待验证 |
| HDTime | `hd_time` | `hd_time.json` | 配置存在，待验证 |
| hdcity | `hdcity` | `hdcity.json` | 配置存在，待验证 |
| News :: Orpheus | — | — | 截图中的外部链接，不属于站点配置 |
| News :: Redacted | — | — | 截图中的外部链接，不属于站点配置 |

## 公开能力项

下表仅表示 JSON 中是否存在对应请求配置，不代表已验证功能可用。

| 站点名称 | user_basic_info | search | sign_in |
|---|---|---|---|
| HDHome | 有 | 有 | 无独立请求项 |
| HDU | 无 | 有 | 有 |
| HDArea | 有 | 有 | 有 |
| OpenCD | 有 | 有 | 有 |
| HDTime | 无 | 有 | 无独立请求项 |
| hdcity | 待核对 | 待核对 | 待核对 |
| News :: Orpheus | 不适用 | 不适用 | 不适用 |
| News :: Redacted | 不适用 | 不适用 | 不适用 |

## 维护范围

- 清单只维护公开站点信息和公开配置状态。
- 截图中重复出现的 `hdcity` 只保留一条。
- “天学/天雪论坛”未列入清单，按用户要求排除。
- 状态为“待验证”时，不代表已进行站点登录或在线功能测试。
- 新发现的个人站点先与 `site_config/sites/*.json` 匹配；没有对应公开配置时，记录为“待新增配置”。
- 不记录私人认证资料，不连接个人 Media Saber 数据库。
