---
title: "[隨筆] 把舊網站重新上線"
date: 2023-10-18T16:21:54+08:00
draft: false
categories: ["隨筆"]
tags: ["Github Page", "Hugo", "Bug", "Hyperlink", "Typing Test"]
weight: 0
---

[昨天]( {{<ref "after-a-long-time.md">}} )嘗試了把這個舊網站重新上線未果。

今天花了不少時間終於發現問題了！因為使用`hugo`指令產生靜態網頁的結果之間的超連結都會以發布的網址最為 baseURL，所以在本機端只能利用`hugo server`指令預覽結果。

另外，將網頁發佈到 Github Page 時，在完成 Push 之後需要一段時間資料才會被放到 Server 上，所以會有一段時間差才會完成更新！這個現象似乎有在計網概提過 🤔

...

這篇文章的最前面用到的超連結，是今天發現的小東西！

在 Hugo 的 markdown 文件中如果需要連結其他文件的話可以使用：

```
{{ <ref "<filename>.md"> }}
```

[more detail](https://gohugo.io/content-management/cross-references/)

...

最近，我囫圇吞棗的在 Codecademy 上學了不少東西，但是發現 HTML 和 CSS 還是不太熟悉，再加上 Javascript 的話，可能就會一團混亂，雖然課程中有安排 project，但我覺得練習量還是不夠。因為最近常在用[Monkeytype](https://monkeytype.com/)和[keybr](https://www.keybr.com/)練習打字，也有找到 Microsoft 的課程[Web-Dev-For-Beginners](https://github.com/microsoft/Web-Dev-For-Beginners)其中有個部分就是實作簡單的 typing test。大概會用個幾天把這個 side project 做出來，也應該會寫點記錄。
