---
title: "RSS簡介與Newsboat的使用"
date: 2021-09-02T17:16:37+08:00
draft: false
categories: ["個人網站"]
tags: ["RSS","Newsboat","Hugo"]
weight: 0
---

### 什麼是RSS?

下面這個[好和弦](https://nicechord.com/)的影片裡有詳細的介紹。

{{< wiwivideo b2fe55c2-f962-4c76-9134-13c246b1aa30 >}}
<br>
4:24 開始介紹Newsboat

### 安裝Newsboat

如果有安裝`snap`，可以直接使用

```
sudo snap install newsboat
```

進入程式之後可以按快捷鍵`?`，查看快捷鍵提示，也可以看[#我的Newsboat設定](/posts/rss_newsboat_hugo/#hugo%E7%B6%B2%E7%AB%99%E7%9A%84rss)自訂快捷鍵。

### Distrotube深入解析Newsboat RSS Reader

因為筆者特別喜歡Newsboat的簡潔版面和方便的鍵盤操作，所以另外又找到這個影片，對Newsboat有更進一步的了解。

{{< youtube2 CJXdQTGm1jg >}}



<a href="#" onclick="playerSeekTo(ytplayer, 106); return false;">1:46</a>

如何編輯 `urls`

<a href="#" onclick="playerSeekTo(ytplayer, 246); return false;">4:06</a>
- 以下都需要用空格隔開
- 自訂標題：在網址的後面加上 "~<YOUR_CUSTOM_TITLE>" 
- 標籤：不需要雙引號，直接輸入你的標籤
- 註解： "!<YOUR_COMMENT>"

<a href="#" onclick="playerSeekTo(ytplayer, 322); return false;">5:22</a>

 youtube channel rss feed

- https://www.youtube.com/feeds/videos.xml?channel_id=
- https://www.youtube.com/feeds/videos.xml?playlist_id=

<a href="#" onclick="playerSeekTo(ytplayer, 475); return false;">7:55</a>

用comment做分類 

<a href="#" onclick="playerSeekTo(ytplayer, 573); return false;">9:33</a>

更多rss

gitlab github 在網址後面加上`.atom`

sourceforge 在網址後加上`/feed`

### 我的Newsboat設定

因為我是用`snap`下載，所以我的設定路徑是在`~snap/newsboat/4780/.newsboat/config`，以下是設定檔的內容：

```
# Ubuntu好像只能這樣設定，會用預設的瀏覽器打開
browser "xdg-open" 
```
可以參考[這個](https://gist.github.com/cirrusUK/f0c880efc242e4751df9)。

### 找到網站或Podcast的RSS連結

大部分有提供RSS的部落格，都會有一個類似wifi的圖示，那個就是他的RSS連結。如果沒有可以嘗試檢視網頁原始碼，搜尋`rss`、`atom`、`xml`或是`url`，有很大的機率可以找到。

Podcast都會用RSS做推播，所以理論上都可以找到各個Podcast的RSS連結。可以用同樣的方法找到RSS連結，但是筆者在Spotify上嘗試過卻找不到。

### Ptt看板的RSS連結

```
https://www.ptt.cc/atom/<BROAD_NAME>.xml
```

### Hugo網站的RSS

Hugo的RSS模板在`layouts/_default/rss.xml`。

產生出來的RSS連結會在`https://<WEBSITE_URLS>/index.xml`。

記得把[我的部落格](/index.xml)加到你的RSS閱讀器喔～～