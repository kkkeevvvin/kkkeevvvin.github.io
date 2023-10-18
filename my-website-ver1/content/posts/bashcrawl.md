---
title: "[遊戲] Bashcrawl介紹"
date: 2021-09-09
estdate: 2021-09-04T09:16:15+08:00
draft: false
categories: ["遊戲"]
tags: ["Bashcrawl","Bash"]
weight: 0
---

### 簡介

這是一個純文字的地牢遊戲，他的呈現方式非常有趣，是用目錄和文件來代表房間和提示，遊玩的方式是用Bash的指令，很適合Bash的初學者玩，在遊戲的過程中，還可以學習到不同的指令使用方式。

### 在開始之前

我們的電腦之中必須有Bash或[Zsh](https://opensource.com/article/19/9/getting-started-zsh)。Linux, BSD和MacOS這些作業系統預設都包含Bash，可以跳過接下來這段。

#### 在Windows安裝Bash

雖然Windows裡面沒有Bash，但是我們有[許多方式](https://superuser.com/questions/608106/how-can-i-use-a-bash-like-shell-on-windows)可以在Windows中安裝Bash。這邊將介紹如何使用[Cygwin](https://en.wikipedia.org/wiki/Cygwin)。

首先點擊下載[setup-x86_64.exe](https://cygwin.com/setup-x86_64.exe)，或是到[官網](https://cygwin.com/install.html)找到適合的版本。

![cygwin](/images/bashcrawl/cygwin.png)

下載好後，按下開啟檔案或是到下載的資料夾中雙擊那個檔案，會出現一個對話框，按下「是」。

![press yes](/images/bashcrawl/press_yes.png)

然後是Cygwin Setup的頁面：

![cygwin setup](/images/bashcrawl/cygwin_setup.png)

不斷的按下一步，直到Choose A Download Site的頁面，這裡隨便挑一個就可以。

![choose download site](/images/bashcrawl/choose_download_site.png)

接下來會出現Select Packages的頁面，左上角有一個`View`的選單，選擇`Full`。在`Search`的框框中輸入`Bash`，按下`Enter`應該就可以看到下圖。最上面的Package就是`Bash`，在`New`的那一欄選擇最新的版本，點擊`Src?`那一欄的框框把它打勾，最後再按個幾次下一步，就會開始安裝。

![search bash](/images/bashcrawl/search_bash.png)

結束安裝之後會出現下圖，按下完成。

![cygwin done](/images/bashcrawl/cygwin_done.png)

桌面上應該會出現一個圖示，點擊就可以在Windows中使用Bash了。

![cygwin icon](/images/bashcrawl/cygwin_icon.png)

### 安裝Bashcrawl

到[官網](https://gitlab.com/slackermedia/bashcrawl/-/tree/master/)或是點擊[這裡](https://gitlab.com/slackermedia/bashcrawl/-/archive/master/bashcrawl-master.zip)下載並且在`下載`裡面解壓縮，不用更動它的名字。（方便後面的操作。）

### 開始遊戲

這邊將以在Windows中使用Cygwin Terminal為例。

首先打開Cygwin Terminal，會看到：

```
blobloblog@MyDesktop ~
$
```

＠前面是你的使用者名稱，@後面是你的電腦名稱，隔一個空格是你當前的目錄(也就是資料夾)，`~`表示是你的家目錄。`$`後面是你可以輸入指令的地方，按下Enter就可送出你的指令。

使用指令：

```
cd c:Users/<YOUR_USERNAME>/Downloads/bashcrawl-master
```

cd是change directory切換目錄，是將你的目錄切換到後面指令的位置。

現在，我們已經到了bashcrawl的目錄，輸入指令`ls`，會出現當前目錄下的檔案：

```
blobloblog@MyDesktop /cygdrive/c/Users/blobloblog/Downloads/bashcrawl-master
$ ls
entrance  LICENSE  README.md
```

有一檔案寫著`README.md`，使用指令`cat`將他所有的內容輸出在終端機中：

```
cat README.md
```

或是使用`less`，可以用方向鍵瀏覽文件內容，按下`q`離開：

```
less README.md
```

仔細閱讀`README.md`，然後使用以下指令開始遊戲：

```
cd entrance/
```

祝大家玩的愉快 ଘ(੭ˊᵕˋ)੭* ੈ✩

#### 參考文件
[https://marlborough-college.gitbook.io/attic-lab/the-terminal/games/level-1-bashcrawl](https://marlborough-college.gitbook.io/attic-lab/the-terminal/games/level-1-bashcrawl)
