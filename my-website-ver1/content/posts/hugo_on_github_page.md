---
title: "將網頁發佈到Github Page"
date: 2021-08-04T09:14:28+08:00
draft: false
categories: ["個人網站"]
tags: ["Hugo","Github","Github page","git"]
weight: 0
---

### 建立Github repository

登入Github的網頁，右上角會看到：

![right upper conner](/images/hugo_on_github_page/right_upper_conner.jpg)

點擊加號，再點擊`New repository`：

![new repo](/images/hugo_on_github_page/new_repo_button.jpg)

出現建立的表單：

![create form](/images/hugo_on_github_page/create_form.jpg)

如果是要作為主要的個人網站，Repository name建議可以使用`<USERNAME>.github.io`。如果你的github repo是命名成`<USERNAME>.github.io`的話，你的網頁就會發布在`<USERNAME>.github.io`；如果不是，會在`<USERNAME>.github.io/<your_repo>`

勾選`Public`，只有付費版本可以用`Private`的repository來建立Github Page。其餘的選項可以自行決定。

最後按下`Create repository`。

<br>

### 上傳到Github repository

如果沒有使用過git，可以先參考[Git 教學(1) : Git 的基本使用](http://gogojimmy.net/2012/01/17/how-to-use-git-1-git-basic/)，完成你的git設定。

這裡以hugo專案預設的存檔路徑`./public`為例。

移動到`public`底下，開始用git管理這個資料夾：

```
git init
```

將所有檔案加入管理：

```
git add .
```

提交修改：

```
git commit -m "first commit"
```

連上自己的github repo，並且做確認：

```
git remote add origin https://github.com/<USERNAME>/<your_repo>.git
git remote -v
```

強制把現在的`branch`變成`main`。
```
git branch -M main
```
然後安裝並登入GitHub Desktop（因為筆者不會設定登入認證），接著 `add local repository`，找到`public`這個資料夾。

`commit`之後就可以`push`到你的Github了。

<br>

### 查看你的網頁

在完成上面的內容以後，打開你的repo的設定：

![setting](/images/hugo_on_github_page/setting.jpg)

在左邊的欄位中找到`Pages`：

![where is Pages](/images/hugo_on_github_page/where_is_pages.jpg)

會出現綠色提示框：

![Pages setting](/images/hugo_on_github_page/pages_setting.jpg)

如果其他部份都設定成功，點擊提示框中的超連結，就可以看到跟`hugo server`產生一樣的網頁了（可能要等伺服器更新）。

### 之後

如果有更動，回到專案目錄用`hugo`產生好網頁，接著到GitHub Desktop一樣是用`commit`和`push`就可以了。

<br>

### 參考文件：

[Build a Personal Website With Github Pages and Hugo](https://levelup.gitconnected.com/build-a-personal-website-with-github-pages-and-hugo-6c68592204c7)

[git --local-branching-on-the-cheap](https://git-scm.com/docs/git-branch)

[Adding an existing project to GitHub using the command line](https://docs.github.com/en/github/importing-your-projects-to-github/importing-source-code-to-github/adding-an-existing-project-to-github-using-the-command-line)
