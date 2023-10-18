---
title: "在Hugo網站中加入留言板"
date: 2021-09-06T11:15:28+08:00
draft: false
categories: ["個人網站"]
tags: ["Hugo","Graphcomment","comments platform"]
weight: 0
---

### 前言

留言板在部落格中是不可或缺的一部分，是讀者回饋作者最直接的方式。因為筆者是目前沒有太大的經濟能力，也沒有架設自己的伺服器，所以選用了有免費試用的第三方服務[Graphcomment](https://graphcomment.com/)，每個月有1,000,000的流量，對小網站來說應該是很夠用了。如果之後要換平台，它也可以匯出所有的留言。

### 申請帳號以及設定

Graphcomment可以直接用Google、Twitter或Facebook登入，也可以用電子郵件註冊。

註冊完以後，按下`Add site`，會出現一個表單：

- Site name: 一個好記的名字就好，讓你自己容易管理各個網站
- Unique ID: 會在之後的部份用到
- Website URL: 就是你的網站URL
- Whitelist domains: 自己決定吧
- Supported language: 好像是壞掉了，之後的設定可以再改

勾選我同意服務條款，按下送出，就完成了一個網站留言版後端的建立了。

接著進入設定，不要點小齒輪圖示，直接點剛才設定的Site name，會進入這個網站留言版後端。點選SETTING，進入Language的頁面選擇留言板的語言，因為沒有繁體中文，所以我是選英文。在Customization頁面中可以調整留言板的顏色，其他的設定也都可以自己調整看看。這個頁面記得先保留，等一下還會用到。

### 將Graphcomment加入Hugo

打開`config.yml`，加入：

```
params:
    GraphCommentId: <YOUR_UNIQUE_ID>
    comments: ture #如果哪天想關掉留言板，改成false就行了
```

在`./layouts/partials`中，加入或修改`comments.html`

```
{{ if ne .Params.comments false }}
    {{ if .Site.Params.GraphCommentId }}
        {{ partial "graphcomment.html" . }}
    {{ end }}
{{ end }}
```

<br>

接著到留言板後端的SETUP，在側邊連點選Universal code，下面有一些選項可以自行調整，然後複製那一段程式碼，回到`./layouts/partials`，新增`graphcomment.html`並且貼上那一段程式碼。

然後找到下面這行：

```
graphcommentId: "<YOUR_UNIQUE_ID>",
```

把他修改成：

```
graphcommentId: {{ .Site.Params.GraphCommentId }}, 
```

記得不要漏掉最後的逗號，因為後面還有其他程式碼需要用逗號隔開。

如果以後要修改GraphCommentId，只需修改`config.yml`裡面的。

<br>

接下來找到：

```
behaviour: {
      // HIGHLY RECOMMENDED
      // uniq identifer for the comments thread on your page (ex: your page id)
```

加入下面一行程式碼：

```
uid: {{ .RelPermalink }}, 
```

這一個部份非常重要，筆者在複製程式碼時，沒有認真看裡面的註解，是在[A小編](https://alittleeditor.com/)的測試之下，發現留言會亂跑到其他篇文章。解決方法就是看清楚註解，加入uid，讓Graphcomment的後端可以分辨是哪一篇文章的留言。

<br>

最後，打開`./layouts/_default/single.html`（這是文章的基本版型），在自己喜歡的位置加上：

```
{{- if (.Param "comments") }}
{{- partial "comments.html" . }}
{{- end }}
```

如果以上的步驟都有正確操作，用`hugo server [-d]`就可以看到留言版囉✧◝(⁰▿⁰)◜✧

### 後記

這是我嘗試的第二個方案，原本是要用staticman + Heroku，但是好麻煩就放棄了。

但是Graphcomment的載入速度有點慢啊<br>(o´Å｀)=з

#### 參考資料

https://graphcomment.com/

[Comments | Hugo](https://gohugo.io/content-management/comments/)

[How to get the URL of the current page with the rel or relref function? | Hugo](https://discourse.gohugo.io/t/how-to-get-the-url-of-the-current-page-with-the-rel-or-relref-function/29113)