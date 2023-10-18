---
title: "Hugo網站的向外連結"
date: 2021-09-05T15:16:39+08:00
draft: false
categories: ["個人網站"]
tags: ["Link","Security","Hugo","New tab"]
weight: 0
---

### 前言

網站中少不了的就是超連結(Hyperlink)，網站中的連結也會影響搜尋引擎優化(Search Engine Optimization)，但是這隱含了網站被跨網站腳本攻擊(XSS)的可能性。

### Hugo link模板

Hugo渲染link的模板在：

```
./layouts/_default/markup/render-link.html
```

如果沒有，自己新增一個就可以了。在裡面加上：

```
<a href="{{ .Destination | safeURL }}"
   {{ with .Title}}
   title="{{ . }}"
   {{ end }}
   {{ if strings.HasPrefix .Destination "http" }}
   target="_blank" {{- /* 在新分頁中開啟連結 */ -}}
   rel="noopener" {{- /* 避免XSS攻擊 */ -}}
   {{ end }}>
    {{ .Text }}
</a>
```



#### 參考資料

[How to Open Link in New Tab | Hugo](https://discourse.gohugo.io/t/how-to-open-link-in-new-tab-with-hugos-new-goldmark-markdown-renderer-in-v0-62-0/22540)

[A小編](https://alittleeditor.com)
