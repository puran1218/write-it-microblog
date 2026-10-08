# 字宝宝 · Write It

**A little Chinese character playground for curious kids.**

Write It（字宝宝）是一款为孩子设计的轻量汉字探索应用：说出、写出或输入一个字，
查看笔顺、跟着描红练习，再把认识的字收进「字本子」。

**[Try the live demo / 在线体验](https://puran.blog/zi/)** ·
**[Source code / 源代码](https://github.com/puran1218/write-it)**

## What can you do?

- **Speak / 说给我听** — use the browser microphone to look up a Chinese character (where supported).
- **Draw / 画给我看** — draw with a finger to see handwriting candidates.
- **Search / 查一查** — search Chinese characters or pinyin.
- **Stroke order & practice / 笔顺与描红** — see animated strokes and practice writing.
- **Character book / 字本子** — keep favorites and celebrate completed practice.

The app uses a static HTML/CSS/JavaScript shell and does not require an account.

## Install on Micro.blog

1. Open your Micro.blog account and choose **Plug-ins → Install plug-in**.
2. Enter the repository URL: `https://github.com/puran1218/write-it-microblog`.
3. Install the plug-in and rebuild your site if necessary.
4. Visit `https://YOUR-BLOG-DOMAIN/zi/`.

**Note:** This plug-in adds an independent page at `/zi/`. It does not
change your blog homepage or navigation. Add a link from your blog if desired.

## Offline use, storage and privacy

Write It caches its app shell and downloaded character data using a Service
Worker. Character data, handwriting index and stroke packs are loaded on demand
from jsDelivr's version-pinned copy of
[puran1218/write-it](https://github.com/puran1218/write-it).
A first visit to a feature may require internet access; an installation does
**not** download every character automatically. Browsers may evict caches.

Practice progress, recently viewed characters and favorites are saved in
your browser's localStorage. Clearing site data or switching devices can
remove that progress. Handwriting recognition runs in the browser.
Voice recognition uses the browser Web Speech API and **may use an online
speech service**, depending on the browser. The microphone is optional:
typing and drawing remain available.

## Maintainers: why this repository is small

This is the **lightweight Micro.blog distribution repository**.
It includes `plugin.json`, HTML, CSS, the compiled `app.js`,
PWA manifest, Service Worker and icons under `static/zi/`.
The large `data/` directory intentionally belongs only to the
[source repository](https://github.com/puran1218/write-it).

To update the compiled app, work in the adjacent `write-it` repository:

```sh
cd ../write-it
npm ci
npm run build
sh scripts/sync-deploy.sh ../write-it-microblog
sh scripts/check-deploy.sh ../write-it-microblog
```

Update the version in **`write-it/plugin.json` first**, then sync.
Commit and push both repos; update/rebuild the plug-in in Micro.blog.
For changes to the version-pinned data, follow the
[source release instructions](https://github.com/puran1218/write-it#发布到-microblog两层仓库架构).

## Credits and licenses

Hanzi Writer program code and character/pen-stroke data are covered by
different upstream licenses. See
[third-party notices and data provenance](https://github.com/puran1218/write-it/blob/main/THIRD_PARTY_NOTICES.md).
