---
title: "在Hugo網站中加入Favicon"
date: 2021-09-05T11:33:30+08:00
draft: false
categories: ["個人網站"]
tags: ["favicon","Hugo","Apple touch icon"]
weight: 0
---

### Favicon是什麼？

[維基百科](https://zh.wikipedia.org/zh-tw/Favicon)是這麼說的：「Favicon是favorites icon的縮寫，亦被稱為website icon（網站圖示）、page icon（頁面圖示）或urlicon（URL圖示）。Favicon是與某個網站或網頁相關聯的圖示。」

Favicon可以讓網站更容易被記得，或是在Android或iOS的手機中藉由「加入主畫面」的功能產生一個web app。

### Hugo後端的設定

只要在`config.yml`中加入：

```
params:
    assets:
        favicon: "<link / abs url>"
        favicon16x16: "<link / abs url>"
        favicon32x32: "<link / abs url>"
        apple_touch_icon: "<link / abs url>"
        safari_pinned_tab: "<link / abs url>"
```

`<link / abs url >`是你的favicon來源，筆者是使用[ICONS8](https://icons8.com/)提供的免費favicon，在這裡直接填入我選擇的favicon的連結。也可以將favicon的檔案儲存在`./static`裡面，但是可能載入的速度會比較慢。

可以藉由修改`./layouts/partials/head.html`更深入的設定favicon的輸出。


#### 參考文件

[Where do I put my favicon with Hugo | stackoverflow](https://stackoverflow.com/questions/42043648/where-do-i-put-my-favicon-with-hugo)

[Adding Custom Favicon(s) | PaperMod](https://adityatelange.github.io/hugo-PaperMod/posts/papermod/papermod-faq/#adding-custom-favicons)

[A小編](https://alittleeditor.com)

