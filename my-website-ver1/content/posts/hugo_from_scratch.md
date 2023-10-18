---
title: "用Hugo製作網頁"
date: 2021-08-03T09:53:04+08:00
draft: false
categories: ["個人網站"]
tags: ["Hugo","Papermod"]
weight: 0
---

### 安裝Hugo

這篇以支援`snap`的Linux版本為例，下載擴充版本的Hugo。

```
snap install hugo --channel=extended
```

其他作業系統可以到 [Install Hugo | Hugo](https://gohugo.io/getting-started/installing) 找到相應的指示安裝。

檢查是否安裝成功：

```
hugo version
```

<!--看要不要用asciinema紀錄指令執行的狀況-->

若要解除安裝：

```
snap remove hugo
```

<br>

### 開始網頁專案

確定安裝好Hugo之後，選好要存放網頁專案的目錄，用指令
> ```
> hugo new site mywebsite -f yml
> ```
>
> - mywebsite可以替換成其他你想要的名字。
>- ` -f yml `指定使用`yml`格式，因為` yml/yaml `的格式比起` toml `更容易閱讀，根據Papermod的作者[adityatelange](https://github.com/adityatelange)的[說法](https://adityatelange.github.io/hugo-PaperMod/posts/papermod/papermod-installation/#intro)，所以以下也將採用` yml `的格式。如果有需要，你可以很容易的找到[YML to TOML](https://search.brave.com/search?q=yml+to+toml&source=desktop)的轉換器。


可以看到hugo幫你建立好的檔案架構如下。

```
mywebsite/
├── archetypes
│   └── default.md
├── config.yml
├── content
├── data
├── layouts
├── static
└── themes
```

### 選擇主題

我選擇的主題是[PaperMod](https://adityatelange.github.io/hugo-PaperMod/)，因為這個主題裡面有很不錯的指引，也有舒服的版面設計。

移動到`mywebsite`底下執行以下指令，把PaperMod的資料複製到`mywebsite/themes/PaperMod`。

```
git clone https://github.com/adityatelange/hugo-PaperMod themes/PaperMod --depth=1
```

接著打開`mywebsite/config.yml`在最後加入

```
theme: "PaperMod"
```

<br>

### 新增文章

```
hugo new posts/my-first-post.md
```

新增的文章會出現在`mywebsite/content/posts/`之下。你可以試著更動`my-first-post.md`，一開始會長這樣：

```
---
title: "My First Post"
date: 2019-03-26T08:47:11+01:00
draft: true
---

```

> 這篇文章如果是草稿就不會發布；如果你想要發布，把它改成`draft: false`。

文章的內容寫在下面的`---`下面，語法可以參考[Basic Syntax | Markdown Guide](https://www.markdownguide.org/basic-syntax/)。

<br>

### 在本機端預覽

在本機開啟一個網頁伺服器：

> ```
> hugo server
> ```
>
> - 在最後加上`-D`，可以預覽草稿
>

用瀏覽器開啟[http://localhost:1313/](http://localhost:1313/)，就可以看到網頁的樣子了。可以放心的更動網頁的內容，只要重新整理網頁，可以馬上看到結果。（可能需要強置重新整理瀏覽器，像是用快捷鍵 Ctrl-R，或者是清除快取。）

<br>

### 產生靜態網頁

Hugo就是用指令`hugo`來產生網頁的：

```
hugo
```

預設的生成結果會在`mywebsite/public/`，可以用`-d`來指定路徑，或是在設定檔`config.yml`中設定`publishdir`。

如果要連同草稿一起產生，加上`-D`。

使用`hugo help`知道更多詳細的參數。

<br>

<br>

### 參考文件

[Quick Start | Hugo](https://gohugo.io/getting-started/quick-start/)

[Installation | PaperMod](https://adityatelange.github.io/hugo-PaperMod/posts/papermod/papermod-installation/)

[Build a Personal Website With Github Pages and Hugo](https://levelup.gitconnected.com/build-a-personal-website-with-github-pages-and-hugo-6c68592204c7)

