---
title: "在Hugo網站中加入Google Analytics"
date: 2021-09-02T16:26:01+08:00
draft: ture
categories: ["個人網站"]
tags: ["Hugo","Google Analytics"]
weight: 0
---

首先可以參考[Google Analytics GA是什麼？](https://www.shopjkl.com/pages/ga)。

取得「評估ID」之後，在 `config.yml` 中加上：

```
googleAnalytics: <YOUR_TRACKING_ID>
```

並且在 `params` 下面加上：

```
env: production
```

接著去點點看你的網站，如果成功的話可以在GA的頁面，看到活動紀錄。