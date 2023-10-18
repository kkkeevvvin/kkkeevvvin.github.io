---
title: "[入門] 圖形使用者界面與命令列界面"
date: 2021-09-09
estdate: 2021-09-06T16:27:30+08:00
draft: false
categories: ["入門"]
tags: ["GUI","CLI"]
weight: 0
---

### 前言

現在的日常生活應該少不了電腦和手機，大家應該會很習慣使用「圖形使用者界面（GUI, Graph User Interface）」。我們可以回想平常都是怎麼使用手機或電腦，我們會看著螢幕中的各種圖示，藉由觸控螢幕、滑鼠或觸控板的操作，得到我們想要的結果，比如說打開應用程式或瀏覽網頁之類的。我們就是依靠「圖形使用者界面」才能這麼做的。

把「圖形使用者界面」這個詞拆開來解釋，「圖形」是我們看到的那些視窗、按鈕、圖示、工具列和選單等等；「使用者界面」則是電腦和我們人類使用者互動的媒介。

然而，使用者界面並不是一開始就是圖形使用者界面。在電腦剛出現的年代是沒有滑鼠的，也沒有強大的運算能力和記憶體可以支援精美的畫面，所以這時候的使用者界面是「命令列界面（CLI, Command-Line Interface）」。

### 命令列界面

如果有看過經典電影《駭客任務》（The Matrix），應該對下面的畫面印象深刻。沒有看過的人可以找個機會去看，你不會後悔的！這個畫面可能會讓人覺得駭客很酷，他們的電腦會閃閃發光，總是在做無法讓人理解的事情。

![The Matrix](/images/intro_cli/the_matrix.png)

但是，駭客或是各種資訊相關工程師他們經常會用到的東西不是長那樣，其實長這樣：

![](/images/intro_cli/Linux_command-line.png)

這個東西就是命令列界面。

使用命令列界面，其實跟使用圖形使用者界面很像，我們的最終目的都是要電腦乖乖聽話，服從我們的指令。在圖形使用者界面中，我們的指令就是點擊螢幕上的某個位置或是其他操作，電腦會做出相對的回應；在命令列界面中，我們的指令會是各種字元的組合，按下Enter之後我們也能得到相應的結果，像是上面那張圖片裡會輸出幾行文字。

### Why CLI

- 節省電腦資源，電腦運行的速度變快
- 熟習操作以後，可以減少使用滑鼠，節省時間
- 方便處理重複且大量的檔案
- 可以更精確的使用電腦
- 在自己的電腦上擁有更大的權限
- 增加電腦使用方式的多樣性

### 打開命令列界面

這邊介紹在Windows和Linux底下打開命令列界面的方法：

#### Windows

Windows下面有兩種原生的命令列界面cmd(Command Prompt,命令提示字元)和PowerShell。後者是Windows開發來取代前者的，詳見[官網文章](https://support.microsoft.com/en-us/windows/powershell-is-replacing-command-prompt-fdb690cf-876c-d866-2124-21b6fb29a45f)。

要開啟這兩種界面，首先按下win鍵打開找到搜尋框：

![windows_search_bar](/images/intro_cli/windows_search_bar.png)

接著，鍵入cmd或PowerShell找到並且按下Enter執行：

![powershell](/images/intro_cli/powershell_and_cmd.png)

![powershell window](/images/intro_cli/powershell_window.png)

![cmd window](/images/intro_cli/cmd_window.png)

但是，這個些並不是今天要介紹的主角，筆者也沒有深入研究過。

#### Linux

我們來看看在Linux底下的命令列界面，它叫做終端機Terminal，跟使用windows一樣，我們在按下Super鍵（沒錯就是Win鍵）叫出搜尋框，搜尋Terminal，按下Enter，下圖以Ubuntu做示範。

![terminal](/images/intro_cli/terminal.png)

![terminal window](/images/intro_cli/terminal_window.png)

我們可以用指令：

```
echo $SHELL
```

可以看出來使用的是哪一種Shell，Shell簡單來說就是指令的解釋器，Shell有很多種類，這裡可以看出來我們使用的是Bash。（[其他方法](https://www.cyberciti.biz/tips/how-do-i-find-out-what-shell-im-using.html)）

![echo shell](/images/intro_cli/echo_shell.png)

### Bash

當我們學習電腦的一個新東西時，我們都希望它不會一直變來變去，不會過時，有越多人在維護越好。

Bash目前是[自由軟體基金會(FSF, Free Software Foundation)](https://www.fsf.org/)的[GNU計畫](https://zh.wikipedia.org/wiki/GNU%E8%A8%88%E5%8A%83)維護的專案。[自由軟體](https://zh.wikipedia.org/wiki/%E8%87%AA%E7%94%B1%E8%BD%AF%E4%BB%B6)，根據自由軟體基金會對其的定義，是一類可以不受限制地自由使用、複製、研究、修改和分發的，尊重使用者自由的軟體。GNU計劃的目標是建立一套完全自由的作業系統，同時開發了大批其他的自由軟體，Bash是其中之一。

Bash有許多優點和廣大的社群支持，筆者認為如果有心學習，在網路上可以找到許多資源。

### 玩個遊戲吧

學習新東西總是讓人無力，沒關係，這裡準備了一個遊戲叫做Bashcrawl，在筆者的另一篇文章有詳細的介紹：[[遊戲] Bashcrawl介紹](/posts/bashcrawl/)。

---

#### 參考資料

[圖形使用者界面 ｜維基百科](https://zh.wikipedia.org/wiki/%E5%9B%BE%E5%BD%A2%E7%94%A8%E6%88%B7%E7%95%8C%E9%9D%A2)

[命令列界面 | 維基百科](https://zh.wikipedia.org/wiki/%E5%91%BD%E4%BB%A4%E8%A1%8C%E7%95%8C%E9%9D%A2)

[GUI | Computer Hope](https://www.computerhope.com/jargon/g/gui.htm)

[Command line vs. GUI | Computer Hope](https://www.computerhope.com/issues/ch000619.htm)
