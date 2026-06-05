---
title: "What is Buroguru?"
description: "Introduction of Buroguru - a blog framework that use Notion as CMS"
thumbnail: "https://prod-files-secure.s3.us-west-2.amazonaws.com/d7df15bf-aa2b-4058-8eb8-6e3e917478e3/1eef75ea-de40-4f47-af86-8f4c7fdfe8f7/image.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Content-Sha256=UNSIGNED-PAYLOAD&X-Amz-Credential=ASIAZI2LB4664R3AVJWK%2F20260605%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20260605T035745Z&X-Amz-Expires=3600&X-Amz-Security-Token=IQoJb3JpZ2luX2VjEJv%2F%2F%2F%2F%2F%2F%2F%2F%2F%2FwEaCXVzLXdlc3QtMiJIMEYCIQCW3lIIR7Iwi3b6x2x9Qj5vF2FCzpAEjZYpB%2FiQz1QcwgIhAKO%2FOOmFw7GAWKA4r0OsjtpvviHlFM6rHdZTJA6%2FixrpKv8DCGQQABoMNjM3NDIzMTgzODA1Igx5rVhw854Gumlui%2Fsq3ANV6D4TBK%2BrDTBAK08RJSpaFZyLDKBRCJRpgAsfsk9ooldXuk5H40Drm8Jkyju0a7aUXPqBJvZCOiM3cTpyx4A6jajOQiVPmvpiPQaY84fpiV%2FfFJ8qvaQUT6MO6AWIvZRkfcl0WyK75d8%2Bn%2Fcg05LK2zdBrttLN%2BNzTMzl4dwQMzvHFi7GaqzRU1n579anMEdznnBDe4iyCe%2FiCdEZ0yl4l4hSbgq3Lm%2FAOeS1YW17vQMtjHsU8cIkA1negFzpjZi1Nl1B%2BOJiS7xG6TqNjgzGg9a9AdsQ7C97uGLVXq89S%2BLBf5JHDiTRjOgbeMyPEKfCbEUDF11RetiGaKgyBpKImXx%2Fe9V7vMthdwtkDmPLK3ZGHO9HUfjND97TJIZL%2BgN1ZD2fXaM6qnas479P5%2BnUEm5FuE1lO51gd8DzbUB1WDNDkxTPiXMoUTZrg8k51RJFaDOMRvoWYv8glHm7NuILEiKaq0IRWtDO9lX53JEXZCgqVNrlc350oQSbYP7xgZeijWumdSQybEFR528rEzmreIQVdUOoQYDC9s8b4M7CRS9%2FTO%2FeSUluRmUsdnVY0LsfE2%2Bk%2Fdf4lXzCHdK%2B2BayYmNIXp9j7ROaCWzNffAsXsS16%2FQLMj%2B2mA1gRTD7%2FojRBjqkAUVNctWLBTb%2Fj9nJgZNUyo6LoEV5HVGgLm%2BDcYpXaPtWbq8PtrdbDiNq2NmfDq0I96sMFd97ch%2FrVgNagY1p%2BkeKKcgmhLhuS4lv3j7vGXAA1n2rr%2BKy1mF0eswydYy%2FSQqssA%2BsJDWupnpnsARcAZMluGWNK9%2F8wwO5rbZWlR6lmc3BuD%2BNLA1StM1TMwoEl9tvUgqrIpLZElwEiJccMbkQyRew&X-Amz-Signature=befb336d6d5268044b232a010029931dc5c9e2e101d8e244bacdc3a6ccec60d9&X-Amz-SignedHeaders=host&x-amz-checksum-mode=ENABLED&x-id=GetObject"
date: "2025-06-23"
tags: ["intro"]
---

# Welcome to **Buroguru** – 用 Notion 創作部落格！


Buroguru lets you blog directly from Notion — clean, simple, and minimal.


---


## 這是什麼 What is this?


Notion 是一款超直覺的筆記與資料管理工具。


Notion is a super intuitive tool for note-taking and organizing information.


我一直覺得它應該有更大的潛力，不只是寫筆記而已。


I’ve always felt it has more potential — beyond just writing notes.


所以我開發了 **Buroguru**，讓你可以直接把 Notion 當作部落格後台來使用。


That’s why I built **Buroguru** — to use Notion as a lightweight CMS for blogging.


設定過程很簡單，幾個步驟就可以開始寫文、發文，乾淨又衛生。


The setup is simple: just a few steps and you’re publishing from Notion — clean and effortless.


---


## 要怎麼用 How to use it?


加入白嫖資源輕量陣營，只需要這三步：


Join the lightweight blogging movement in just three steps:

- 建立 Notion 資料庫與整合

	Create a Notion database and integration

- Fork [這個 repository](https://github.com/WuSandWitch/Buroguru)，設定幾個 key

	Fork [this repository](https://github.com/WuSandWitch/Buroguru) and configure a few keys

- 調整設定檔來客製化你的部落格外觀

	Customize your blog through the config file


📚 詳細教學請看：[快速開始 Quick Start](https://buroguru.zudo.cc/posts/get-started-en)


---


## 它是怎麼運作的 How it works?


Buroguru 透過腳本與 Notion API 溝通，取得內容並轉成 markdown。


Buroguru fetches content from Notion via API and renders it as markdown.


前端使用 Next.js，自動部署在 Vercel 上。


The frontend runs on Next.js and is auto-deployed via Vercel.


GitHub Actions 每 8 小時會自動同步與重新部署，完全免操作。


GitHub Actions syncs and redeploys every 8 hours — no manual work needed.


你只要在 Notion 寫文，剩下交給它搞定 ✨


You just write in Notion. Everything else is handled for you ✨


---


## 最後 One more thing


如果你喜歡這個專案，歡迎幫我按個 GitHub ⭐️，對我會是很大的鼓勵。


If you find this project helpful, consider leaving a ⭐️ on GitHub — it really means a lot.


有任何問題或想法，歡迎開 issue 或直接聯絡我 👉 [Owen Wu](https://wusandwitch.zudo.cc/)


Feel free to open an issue or reach out to me 👉 [Owen Wu](https://wusandwitch.zudo.cc/)


Let’s make blogging as smooth as writing notes. 💡


讓寫部落格，變得像寫筆記一樣自然。💡

