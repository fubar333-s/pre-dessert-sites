# 本 fork 说明（fubar333-s/pre-dessert-sites）

本仓库 fork 自 [mantou568/pre-dessert-sites](https://github.com/mantou568/pre-dessert-sites)，供自用的 Media Saber 拉取站点配置：

```
configsUrl: https://github.com/fubar333-s/pre-dessert-sites/archive/main.zip
```

## 同步上游

- `.github/workflows/sync-upstream.yml` 每天北京时间 07:30 把上游 `main` 合并进本仓库 `main`，合并后触发 `release.yml` 生成新 Release（Media Saber 按 Release 拉取）；也可在 Actions 页面手动运行。
- 与上游冲突时运行失败，不会覆盖本仓库的修改；需要人工合并后推送。
- 如果上游修改了 `.github/workflows/` 下的文件，`GITHUB_TOKEN` 无权推送这类文件，同步也会失败，需要人工合并。

## 本仓库相对上游的修改

| 日期 | 文件 | 修改 | 原因 |
|---|---|---|---|
| 2026-11-22 | `site_config/sites/red.json` | `required.sign_in`: `true` → `false` | RED（Gazelle）没有 `attendance.php`，签到报 404；改为只模拟登录 |
| 2026-11-22 | `site_config/sites/hdc.json`（id `hdwing`，瓷） | `required.sign_in`: `true` → `false` | 上游已把 `sign_in` 请求设为 `disabled`，但 `required.sign_in` 仍为 `true`，MS 签到时空指针 panic（`np_client.go:419`） |
| 2026-11-22 | `site_config/sites/rousi.json` | 签到成功正则增加 `^success$` | 签到接口成功时返回 `{"code":0,"message":"success"}`，原正则只认中文，成功也被判失败 |
| 2026-11-22 | `site_config/sites/piggo.json` | `user_basic_info.is_login` 改为 `code` eq `0` | 原规则对数字型 `data.user.id` 用 `not_blank`，登录成功仍判“未登录”（推测，见验证记录） |

适合上游的修改可以再向上游提 PR；上游合并后，本表对应行可删除。
