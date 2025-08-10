---
title: "快速開始：用十分鐘設定你的部落格"
description: "設定你的 Buroguru 教學"
thumbnail: "/images/posts/6deb6b68-66d5-407d-80eb-4e17e04cd148.png"
date: "2025-06-22"
tags: ["tutorial"]
---

### [English Version](https://buroguru.zudo.cc/posts/get-started-en)


# 如果你還不認識 Buroguru…


請先參考這篇介紹：[什麼是 Buroguru？](https://buroguru.zudo.cc/posts/intro)


這是一份教你如何使用 Buroguru 快速部署自己 Notion 部落格的教學。


## Step 1：建立資料庫


在部署 Buroguru 之前，你需要準備一個 Notion 資料庫作為部落格的內容來源。你可以[複製這個模板](https://www.notion.so/21ad51c831448068b621f3b5def5dd2d)，或依照下列欄位自行建立：


| 欄位名稱          | 類型            | 說明                                                          |
| ------------- | ------------- | ----------------------------------------------------------- |
| `Title`       | Title         | 文章標題                                                        |
| `id`          | Text          | 文章的 ID，也是文章的網址尾段（slug），例如 `buruguru.zudo.cc/get-started-zh` |
| `Published`   | Checkbox      | 是否發佈                                                        |
| `Tags`        | Multi-select  | 分類標籤                                                        |
| `Date`        | Date          | 發佈時間                                                        |
| `Description` | Text          | 預覽時顯示的摘要                                                    |
| `Thumbnail`   | Files & media | 縮圖圖片                                                        |


## Step 2：設定 Notion Integration


為了讓 Buroguru 存取你的 Notion 資料庫，我們需要建立一個 Notion Integration 並取得金鑰。

1. 建立新的 Integration

	前往 [Notion Integration 頁面](https://www.notion.so/profile/integrations)，點選「Add Integration」，選擇資料庫所在的 workspace，並輸入名稱，例如 `blog`，logo 可略。


	![image.png](/images/posts/3960ee7e-2593-44b5-b052-2e6ab9f6caea.png)

2. 開啟權限

	點進剛新增的 Integration，在 **Content Capabilities** 區塊中，至少開啟 **Read content** 權限。


	![image.png](/images/posts/71103e01-2a49-4555-bac0-c29cf9f657f9.png)

3. 複製 Notion token

	建立後你會看到 **Internal Integration Token**，請複製這個 Token，稍後會使用。


	![image.png](/images/posts/b8560bbb-bcfb-42dd-b975-d760b65d43ab.png)

4. 加入資料庫連線

	回到你剛剛建立的 Notion 資料庫（需為 full page），點右上角三點 → 選擇 **Connections**，並選擇剛剛建立的 Integration。


	![image.png](/images/posts/1ab78b09-8211-45bb-9397-1a9ab394ccc8.png)


	![image.png](/images/posts/8dbb6401-3f21-4f1e-b0d4-de8c595bc96e.png)

5. 複製資料庫 ID

	點選右上角的 **Share** → **Copy Link**，你會獲得一個類似這樣的連結：


	[`https://www.notion.so/wusandwitch-notes/212d51c8314480ca8d4ffa62487XXXXXX?v=...`](https://www.notion.so/212d51c8314480ca8d4ffa624873e734)


	![image.png](/images/posts/9dbf7cd8-b203-48e4-b19c-ac4be6466f31.png)


	`Database ID` 就是 `?` 前的那段 ID，例如上方範例為 `212d51c8314480ca8d4ffa62487XXXXXX`，請記下來，等等會用到。


## Step 3：建立 Repository 並設定 Secrets


當 Notion 整合完成後，你可以 fork Buroguru 專案並開始部署。

1. Fork 專案

	前往 [https://github.com/WuSandWitch/Buroguru](https://github.com/WuSandWitch/Buroguru) 並點選 **Fork**


	替你的 repo 命名，例如 `WuSandWitch-Blog` 。


	![image.png](/images/posts/77b5c3bc-93c5-4b16-8364-fdad49906217.png)

2. 設定 GitHub Secrets / Notion Token

	Fork 完成後，前往 **Settings → Secrets and variables → Actions**，然後點選 **New repository secret**


	![image.png](/images/posts/d94e158f-2308-4354-9519-ace9d0a76f3f.png)


	![image.png](/images/posts/52f79ba0-e1d3-4db0-a2b3-ece8324d7bd6.png)


	新增一個名稱為 `NOTION_TOKEN` 的 Secret，值為剛剛複製的 Notion Integration Token。


	![image.png](/images/posts/c05d3693-20e5-404c-a413-e26d08b075e4.png)


	再新增一個 Secret 名稱為 `NOTION_DATABASE_ID`，值為你剛剛記下的資料庫 ID。


	![image.png](/images/posts/86413755-f5a2-4126-8c9b-7d15b5b9dd1b.png)


## Step 4：部署到 Vercel


現在你已經設定好 GitHub repo 和環境變數，接下來我們要將專案部署到 [Vercel](https://vercel.com/)！


登入後，點選 **+ Add New Project**，然後選擇你 fork 的 repo（例如 `WuSandWitch-Blog`）


![image.png](/images/posts/993b3327-b853-4b02-b1fc-918fe48098bf.png)


![image.png](/images/posts/80ab7783-fc85-4435-9a5a-70b24fb09ad7.png)


按下 **Deploy** 即可部署，幾秒鐘後你的部落格就會正式上線！


![image.png](/images/posts/54559433-0603-4522-9fdf-5fef6d968b50.png)


## 下一步：個人化你的部落格


你可以在 config 檔案裡面設定你的部落格，[教學看這ㄦ](https://buroguru.zudo.cc/posts/config-guide-zh)


## ⏱ 自動更新機制


部署完成後，Buroguru 會透過 GitHub Actions **每 12 小時自動同步 Notion 資料並重新部署**，你不需要額外操作。


如果需要立即更新，也可以到 GitHub 專案的 **Actions** 分頁手動觸發 workflow。


## 🗣 有問題嗎？


如果你在部署過程中遇到任何問題，歡迎透過[這裡](https://wusandwitch.zudo.cc/)提供的聯絡方式私訊我！


如果你覺得這個專案對你有幫助，請幫我在 GitHub 上按個 ⭐️，我會非常感謝！

