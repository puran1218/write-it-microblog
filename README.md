# write-it-microblog — 字宝宝 · Write It 的 micro.blog 部署壳

这是「字宝宝 · Write It」在 micro.blog 上安装用的**轻量部署仓库**：
只包含插件清单和应用壳（`plugin.json` + `static/zi/` 的 index/app/styles/
Service Worker/图标），**不包含任何数据文件**——这是刻意为之，
让 micro.blog 只需要克隆几百 KB。

## 数据从哪来

静态数据（字典 9565 字、笔顺分包、手写识别索引）由 jsDelivr 直接从
主仓库 [puran1218/write-it](https://github.com/puran1218/write-it) 按版本
tag 分发（当前 `data-v1`），应用运行时按需拉取并缓存在设备上。
详见主仓库 README 的「发布到 Micro.blog」章节。

## 更新这个仓库

主仓库构建后运行：

```sh
../microblog-zi/scripts/sync-deploy.sh
```

然后 commit + push，micro.blog 会自动重新拉取。
