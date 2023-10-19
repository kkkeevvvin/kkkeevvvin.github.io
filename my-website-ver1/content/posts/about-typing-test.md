---
title: "[隨筆]關於打字練習網站"
date: 2023-10-19T22:05:28+08:00
draft: false
categories: ["隨筆"]
tags: ["Typing Test", "CSS", "JavaScript", "TypeScript", "Keybroad", "Future"]
weight: 0
---

昨天後來就開始做我的打字練習網站[MyType](https://kkkeevvvin.github.io/Typing-Test/)。發現昨天說的[課程](https://github.com/microsoft/Web-Dev-For-Beginners/tree/main/4-typing-game/typing-game)內容挺詳細的，其實只要把東西複製貼上就做完了八成，原本的 JavaScript 就已經能動了，剩下的就是寫 CSS 讓版面好看一點，微調一下 JavaScript。

認真看了下 git log，做了比較有用的事有：

- 讓輸入錯誤的字顯示紅色
- 關掉輸入框的 autocomplete
- 結束時把 highlight 的單字還原，清空輸入框
- 從第一個輸入開始計時，若重新開始時重設計時器
- 還算好看的排版

心得是怎麼才寫一點點 code，整陀 code 就亂七八糟。

...

有人跟我說可以做中文的打字練習，然後有鍵盤的。去參考了其他網站，發現這是要鍵盤一顆一顆自己刻出來，還是有什麼聰明的方法我還沒想到...
或許可以用 CSS Grid?

...

看了看其他打字練習網站之後的想法：

中文打字的介面都好醜(無意冒犯...)，感覺有一些時間沒人在做這個東西。

[typings.gg](https://typings.gg/)全部都是用 JavaScript 刻出來的。[最新的 issue](https://github.com/briano1905/typings/issues/112)有人在問這個 project 還活著嗎，有人回說 owner 超久沒上線了，其他活人也都跑去 MonkeyType。

因為[MonkeyType](https://github.com/monkeytypegame/monkeytype)和[Keybr.com](https://github.com/aradzie/keybr.com)都是用 TypeScript，查了一下是跟 JavaScipt 有點像的東西。感覺我可以先參考 typings.gg，多做一些功能，看看 code style 有沒有可以學習的地方，之後再看看吧。

...

打字練習還有市場嗎？除了上班族和工程師，有什麼人會需要常常用到鍵盤，而且還需要速度快？

Vision Pro 隨然沒有實體鍵盤，但還是有虛擬鍵盤，用攝影機去偵測手的位置。

如果未來變成偵測腦波來輸入的話？電競變成腦波大賽？

查了才發現 2018 年就有人在想這件事了，[The future of typing doesn’t involve a keyboard](https://qz.com/1468577/the-future-of-typing-doesnt-involve-a-keyboard)，還未細讀。
