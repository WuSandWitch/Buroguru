---
title: "快速開始：用十分鐘設定你的部落格"
description: "設定你的 Buroguru 教學"
thumbnail: "/images/posts/eca7ed77-e044-4ff8-9e5e-9dac5a61155e.png"
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


	![image.png](/images/posts/e2f1c20e-3629-41a3-a9fe-2d6f2a56307a.png)

2. 開啟權限

	點進剛新增的 Integration，在 **Content Capabilities** 區塊中，至少開啟 **Read content** 權限。


	![image.png](/images/posts/deb668fc-93b2-4e9c-8a3a-ad6724568266.png)

3. 複製 Notion token

	建立後你會看到 **Internal Integration Token**，請複製這個 Token，稍後會使用。


	![image.png](/images/posts/9dbb3a1a-02b3-4609-b394-a8796399ac65.png)

4. 加入資料庫連線

	回到你剛剛建立的 Notion 資料庫（需為 full page），點右上角三點 → 選擇 **Connections**，並選擇剛剛建立的 Integration。


	![image.png](/images/posts/3105c10d-0d26-410a-9240-19be51ad3145.png)


	![image.png](/images/posts/24945dbf-d78e-4215-8a16-e57c4cd6cb4c.png)

5. 複製資料庫 ID

	點選右上角的 **Share** → **Copy Link**，你會獲得一個類似這樣的連結：


	[`https://www.notion.so/wusandwitch-notes/212d51c8314480ca8d4ffa62487XXXXXX?v=...`](https://www.notion.so/212d51c8314480ca8d4ffa624873e734)


	![image.png](/images/posts/dab359d4-c575-4e48-bf06-bfe29ee3d051.png)


	`Database ID` 就是 `?` 前的那段 ID，例如上方範例為 `212d51c8314480ca8d4ffa62487XXXXXX`，請記下來，等等會用到。


## Step 3：建立 Repository 並設定 Secrets


當 Notion 整合完成後，你可以 fork Buroguru 專案並開始部署。

1. Fork 專案

	前往 [https://github.com/WuSandWitch/Buroguru](https://github.com/WuSandWitch/Buroguru) 並點選 **Fork**


	替你的 repo 命名，例如 `WuSandWitch-Blog` 。


	![image.png](/images/posts/e0b05079-a9f6-4e29-a032-d94eb329de2e.png)

2. 設定 GitHub Secrets / Notion Token

	Fork 完成後，前往 **Settings → Secrets and variables → Actions**，然後點選 **New repository secret**


	![image.png](/images/posts/aca7df47-afb2-4ae5-bfa0-94ded0e8c946.png)


	![image.png](/images/posts/db029c80-1b2c-4e60-8b36-6cfcfb361607.png)


	新增一個名稱為 `NOTION_TOKEN` 的 Secret，值為剛剛複製的 Notion Integration Token。


	![image.png](/images/posts/91354e8e-169b-4e39-bedd-671b3a823e57.png)


	再新增一個 Secret 名稱為 `NOTION_DATABASE_ID`，值為你剛剛記下的資料庫 ID。


	![image.png](/images/posts/f1aff33b-a9f3-4139-9faa-0d99ba98ea76.png)


## Step 4：部署到 Vercel


現在你已經設定好 GitHub repo 和環境變數，接下來我們要將專案部署到 [Vercel](https://vercel.com/)！


登入後，點選 **+ Add New Project**，然後選擇你 fork 的 repo（例如 `WuSandWitch-Blog`）


![image.png](/images/posts/28110d02-5616-4f6d-bacf-1e38acbef425.png)


![image.png](/images/posts/436e18b3-2c4d-412f-8850-3eee95e3328f.png)


按下 **Deploy** 即可部署，幾秒鐘後你的部落格就會正式上線！


![image.png](/images/posts/36d074e4-0bb1-4eb1-94ea-b7c5f9d91929.png)


## 下一步：個人化你的部落格


你可以在 config 檔案裡面設定你的部落格，[教學看這ㄦ](https://buroguru.zudo.cc/posts/config-guide-zh)


## ⏱ 自動更新機制


部署完成後，Buroguru 會透過 GitHub Actions **每 12 小時自動同步 Notion 資料並重新部署**，你不需要額外操作。


如果需要立即更新，也可以到 GitHub 專案的 **Actions** 分頁手動觸發 workflow。


## 🗣 有問題嗎？


如果你在部署過程中遇到任何問題，歡迎透過[這裡](https://wusandwitch.zudo.cc/)提供的聯絡方式私訊我！


如果你覺得這個專案對你有幫助，請幫我在 GitHub 上按個 ⭐️，我會非常感謝！

