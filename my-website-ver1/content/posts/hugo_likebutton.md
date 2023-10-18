---
title: "在Hugo網站中加入LikeButton"
date: 2021-08-31T16:10:27+08:00
draft: false
categories: ["個人網站"]
tags: ["Hugo","LikeCoin","LikeButton"]
weight: 0
---


不知道什麼是Likecoin的人可以先去看看[這篇文章](https://richard23.com/what-is-likecoin/)。

這篇文章主要是參考[Hugo 安裝 LikeCoin 教學 | WANcatServer](https://wancat.cc/post/hugo-install-likecoin/#%E6%8F%92%E5%85%A5-likecoin)。

Hugo 可以使用自訂 Layout 的方式，在不改變主題的情況下改變網站設計，我們可以透過這個方式在每個文章下放置 LikeButton。

為了覆寫文章輸出的模板，將 theme 的 layouts 資料夾複製到專案目錄下。
```
cp -r theme/<YOUR_THEME>/layouts/ .
```
Hugo 中的 Partial 功能，可以讓你建立小模板，嵌入在頁面中。[參考文件](https://gohugo.io/templates/partials/)。

在 layouts 的 partials 資料夾建立 likecoin.html，寫入以下內容。你也可以在這裡加上想給讀者看的說明文字（HTML格式）。

```
<iframe class="LikeCoin" height="235" src="https://button.like.co/in/embed/{{ .Site.Params.likerID }}/button?referrer={{ .Permalink }}" width="100%" frameborder=0></iframe>
```

接下來在 config.yml 的params後面加入

```
likerID = "<your liker id>"
```

接著編輯文章使用的模板，通常是 _default/single.html。這就是一個 Go Template，在你想要的地方插入：

```
{{ partial "likecoin.html" . }}
```

建議插在 `{{ .Content }}` 後面，Like Button 就會接在文章後面。

Go Template裡面有很多花括號，讓人眼花撩亂，我使用的主題在 `{{ .Content }}` 附近的程式碼如下：

```
  <div class="post-content">
    {{- if not (.Param "disableAnchoredHeadings") }}
    {{- partial "anchored_headings.html" .Content -}}
    {{- else }}{{ .Content }}{{ end }}
    <!-- likecoin below -->
    {{ partial "likecoin.html" . }}
  </div>
```

如果把上述那段程式碼緊接著插入在 `{{ .Content }}`後，會造成LikeButton有時候不會出現。Go語言的程式邏輯和大多數的程式語言都一樣，在插入時要看清楚附近的程式碼。

這樣 Hugo 就會將 likecoin 這個 partial render 到你的文章中了。記得加上 “."，沒有的話，likecoin 的模板讀不到資料。整個過程都不需要動到 theme 的原始程式。

最後，執行 hugo server 預覽你的網站。

<br>

<a rel=license href=http://creativecommons.org/licenses/by-sa/3.0/tw/><img alt="創用 CC 授權條款" style=border-width:0 src=https://i.creativecommons.org/l/by-sa/3.0/tw/88x31.png></a>
本著作係採用<a rel=license href=http://creativecommons.org/licenses/by-sa/3.0/tw/>創用 CC 姓名標示-相同方式分享 3.0 台灣 授權條款</a>授權.

