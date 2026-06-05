---
title: "快速開始：用十分鐘設定你的部落格"
description: "設定你的 Buroguru 教學"
thumbnail: "https://prod-files-secure.s3.us-west-2.amazonaws.com/d7df15bf-aa2b-4058-8eb8-6e3e917478e3/1eef75ea-de40-4f47-af86-8f4c7fdfe8f7/image.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Content-Sha256=UNSIGNED-PAYLOAD&X-Amz-Credential=ASIAZI2LB4664R3AVJWK%2F20260605%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20260605T035745Z&X-Amz-Expires=3600&X-Amz-Security-Token=IQoJb3JpZ2luX2VjEJv%2F%2F%2F%2F%2F%2F%2F%2F%2F%2FwEaCXVzLXdlc3QtMiJIMEYCIQCW3lIIR7Iwi3b6x2x9Qj5vF2FCzpAEjZYpB%2FiQz1QcwgIhAKO%2FOOmFw7GAWKA4r0OsjtpvviHlFM6rHdZTJA6%2FixrpKv8DCGQQABoMNjM3NDIzMTgzODA1Igx5rVhw854Gumlui%2Fsq3ANV6D4TBK%2BrDTBAK08RJSpaFZyLDKBRCJRpgAsfsk9ooldXuk5H40Drm8Jkyju0a7aUXPqBJvZCOiM3cTpyx4A6jajOQiVPmvpiPQaY84fpiV%2FfFJ8qvaQUT6MO6AWIvZRkfcl0WyK75d8%2Bn%2Fcg05LK2zdBrttLN%2BNzTMzl4dwQMzvHFi7GaqzRU1n579anMEdznnBDe4iyCe%2FiCdEZ0yl4l4hSbgq3Lm%2FAOeS1YW17vQMtjHsU8cIkA1negFzpjZi1Nl1B%2BOJiS7xG6TqNjgzGg9a9AdsQ7C97uGLVXq89S%2BLBf5JHDiTRjOgbeMyPEKfCbEUDF11RetiGaKgyBpKImXx%2Fe9V7vMthdwtkDmPLK3ZGHO9HUfjND97TJIZL%2BgN1ZD2fXaM6qnas479P5%2BnUEm5FuE1lO51gd8DzbUB1WDNDkxTPiXMoUTZrg8k51RJFaDOMRvoWYv8glHm7NuILEiKaq0IRWtDO9lX53JEXZCgqVNrlc350oQSbYP7xgZeijWumdSQybEFR528rEzmreIQVdUOoQYDC9s8b4M7CRS9%2FTO%2FeSUluRmUsdnVY0LsfE2%2Bk%2Fdf4lXzCHdK%2B2BayYmNIXp9j7ROaCWzNffAsXsS16%2FQLMj%2B2mA1gRTD7%2FojRBjqkAUVNctWLBTb%2Fj9nJgZNUyo6LoEV5HVGgLm%2BDcYpXaPtWbq8PtrdbDiNq2NmfDq0I96sMFd97ch%2FrVgNagY1p%2BkeKKcgmhLhuS4lv3j7vGXAA1n2rr%2BKy1mF0eswydYy%2FSQqssA%2BsJDWupnpnsARcAZMluGWNK9%2F8wwO5rbZWlR6lmc3BuD%2BNLA1StM1TMwoEl9tvUgqrIpLZElwEiJccMbkQyRew&X-Amz-Signature=befb336d6d5268044b232a010029931dc5c9e2e101d8e244bacdc3a6ccec60d9&X-Amz-SignedHeaders=host&x-amz-checksum-mode=ENABLED&x-id=GetObject"
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


	![image.png](/images/posts/8c127726-c854-4190-b3ba-38511a9d727f.png)

2. 開啟權限

	點進剛新增的 Integration，在 **Content Capabilities** 區塊中，至少開啟 **Read content** 權限。


	![image.png](/images/posts/a3928144-2ba6-409c-9991-3f9aab01993f.png)

3. 複製 Notion token

	建立後你會看到 **Internal Integration Token**，請複製這個 Token，稍後會使用。


	![image.png](/images/posts/9b41bbc2-6ba5-4a96-a344-589a26befb63.png)

4. 加入資料庫連線

	回到你剛剛建立的 Notion 資料庫（需為 full page），點右上角三點 → 選擇 **Connections**，並選擇剛剛建立的 Integration。


	![image.png](/images/posts/83a1a849-8312-4af2-83b7-8fcd0972f6e7.png)


	![image.png](/images/posts/b16e284f-39bc-458e-96c2-7ba839ecc3b4.png)

5. 複製資料庫 ID

	點選右上角的 **Share** → **Copy Link**，你會獲得一個類似這樣的連結：


	[`https://www.notion.so/wusandwitch-notes/212d51c8314480ca8d4ffa62487XXXXXX?v=...`](https://www.notion.so/212d51c8314480ca8d4ffa624873e734)


	![image.png](/images/posts/d20b717f-34ae-4a77-8e6b-2d455810bda3.png)


	`Database ID` 就是 `?` 前的那段 ID，例如上方範例為 `212d51c8314480ca8d4ffa62487XXXXXX`，請記下來，等等會用到。


## Step 3：建立 Repository 並設定 Secrets


當 Notion 整合完成後，你可以 fork Buroguru 專案並開始部署。

1. Fork 專案

	前往 [https://github.com/WuSandWitch/Buroguru](https://github.com/WuSandWitch/Buroguru) 並點選 **Fork**


	替你的 repo 命名，例如 `WuSandWitch-Blog` 。


	![image.png](/images/posts/935f2185-604f-4150-ac15-2262cc90176b.png)

2. 設定 GitHub Secrets / Notion Token

	Fork 完成後，前往 **Settings → Secrets and variables → Actions**，然後點選 **New repository secret**


	![image.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/d7df15bf-aa2b-4058-8eb8-6e3e917478e3/afb41d59-6547-49d6-832e-9fa56c0da652/image.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Content-Sha256=UNSIGNED-PAYLOAD&X-Amz-Credential=ASIAZI2LB4664EK775FD%2F20260605%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20260605T040442Z&X-Amz-Expires=3600&X-Amz-Security-Token=IQoJb3JpZ2luX2VjEJv%2F%2F%2F%2F%2F%2F%2F%2F%2F%2FwEaCXVzLXdlc3QtMiJHMEUCIQD3dsdBZBWx9A4xyqstOUjpchwy1tlKorMS6%2B2lhhZTdwIgIXCye1jCFlVmfwRu6hIUgqxuwljt9sagU206cpESd0Yq%2FwMIZBAAGgw2Mzc0MjMxODM4MDUiDEpq%2Fxi%2BiluPOR0fAyrcA4%2F48GEhCLIFwljLJJX5GJxoHo6sf%2BXmXvdYVxkci6OmHOuuHtpXFHjnGGeGmds0NHJFrumR5P%2FK%2BS0TuxnsD17WvUM1KEBHI49Io3%2B90eXG1aHK27te3YNQn0n6OJtE8EmWkDktecxxGQe30L2RMveA%2BMzGmBdnmZoXSG1HY8bgoIpKsWDMKT7Y4sZfrRSS0QqS9kU9%2FU0WWCGUOu6Oi3VqYwO1z14QqiXxNGv2nF7CjPFfq8SQ2trv0xgsqXm%2FZJWfXH9ukrCeXJWm7Ha%2FogpeJJVYk77%2FYfksUzVIzvQB%2FZhIX%2BguE3l10H0dLntNp9pYd2KXvFhg0v8wedz7%2Fbp7rBMIdPV21DoPkMsKjLnIoPzWXaaYc1qlTI8A0ZatC%2F8HzRxiCsiWH7PqBM7VwToMbAbUsidOeo06Bf%2BMkX0tuESCEe9Mrff5Bru9z%2B1dckdUSoIZU47Lp9N4qMkSjlryMhg0TmBJPZx6ymjnnq1aL7RTnuklUq4JyMEZHywPLQmcqdGRgv64CZWuYINgWIfyr1bfnkdSICGnf10TNbpu4WzsMXznDDZ%2FwOPGKudYvusFyZ9ScQefBtKPPgygcdRXAYmNiC2CEuBwSxsNtKrYdK%2B2vkLcK1TvXlF%2BMNj%2BiNEGOqUB8X3OY2kfVie0TtxyXJV684iIyDQDWavgBxm3RU6uenE47V4nGgAyDmWtVvvx5tob0dESsrdI60qdjiiE7KNx3PUowOPJODVNz4RX56Il52LeBC%2FmfxEBCjRd2%2FEqlVB711oWJAfRYzYATFH8S4tNsLznbqEQxL26mhzQivyaejW0uLXZoPC%2BLLC7nMe44EBMy5zXDCU6RZhFxR0xWwY1Y81Zhnnv&X-Amz-Signature=8f94acd38d3ac65f3eca11a696872231e724b8296baf0baa4e1ebfb981908a95&X-Amz-SignedHeaders=host&x-amz-checksum-mode=ENABLED&x-id=GetObject)


	![image.png](/images/posts/2659ae5d-2445-477f-a57a-4f0f23473e88.png)


	新增一個名稱為 `NOTION_TOKEN` 的 Secret，值為剛剛複製的 Notion Integration Token。


	![image.png](/images/posts/e3700203-99d4-4769-9121-9a759adb28b5.png)


	再新增一個 Secret 名稱為 `NOTION_DATABASE_ID`，值為你剛剛記下的資料庫 ID。


	![image.png](/images/posts/293c1d61-89c5-4902-b712-87f4aef29d79.png)


## Step 4：部署到 Vercel


現在你已經設定好 GitHub repo 和環境變數，接下來我們要將專案部署到 [Vercel](https://vercel.com/)！


登入後，點選 **+ Add New Project**，然後選擇你 fork 的 repo（例如 `WuSandWitch-Blog`）


![image.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/d7df15bf-aa2b-4058-8eb8-6e3e917478e3/863a15a2-e286-4de5-9690-69a9c2b34078/image.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Content-Sha256=UNSIGNED-PAYLOAD&X-Amz-Credential=ASIAZI2LB466QJK3ONL2%2F20260605%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20260605T040439Z&X-Amz-Expires=3600&X-Amz-Security-Token=IQoJb3JpZ2luX2VjEJv%2F%2F%2F%2F%2F%2F%2F%2F%2F%2FwEaCXVzLXdlc3QtMiJIMEYCIQCx4LAXQosNFIozmrLu5%2FMHOn7dlQNmWEWTzLIThbZhdwIhAPxBKF2Gl2m4aaMfNnqZcTsFX4veFvD2egZY7krydQ5oKv8DCGQQABoMNjM3NDIzMTgzODA1Igw3nWuKJgwQ%2FAZdiF8q3AOIgTGAgkiqdMs%2BJ0ve1T61eToUD8lI1jPJbTlV9lOW9ERBys98YFWOCHHZKQpfa9YXxt773rlSC09SL%2BZNOCAVHp%2B1wCNTiRXVqi6bGnRGh7E91OJ2Y%2FnIF4B%2BpgR8aJiwCBPJfutfSrC2JIMirO05w7kXL%2FSAk4DRBK%2BOhU0tv47ujJ%2BrzD2u%2BuBGjnscgew5T9ge0Ju34RCIuAw3x%2FNUqKGXSti0nBkcpiPDyr7EEbqHCKOnO2%2FIs3OnUZ3AMJ4QfzCTKuux9y5LzHsNgYqFg%2FOyPIoizUntj3TYzkGT%2BniGSLk%2BV0b5rx80j9j4bIt7Vgfot3UXbW%2FMn0fpqvTWrDO%2B1Fl6jv94gVqgoyHp71SQN%2BQnoH6aJrUgnaUaGVtvBBN8ODq9ZsgfxyLxyHI9VVmpiyNl4vnQ9XMGmvYfOq9Gf76TkA2q%2B2C6f61YGbwFOJUazKht%2BaoNUiwQZD284owBevF2EBcb69cmP0KwdQ6s04KueLgVkiy%2FCdIfJ8TYol1x3YjyIvbt9IcwQaBZcPlAjLHBL6g91RMeNVc0%2FJ2E%2Fo1PhvaLwPbnfQDFNRZCyR0u97o2XjUBcDzdkI60Hi5QiKjchPddMtio7w1nQytOvxFwRjJBlO2x%2BDCQ%2F4jRBjqkAWv%2Bp8B2XMZP9RuQBDCudO1OLQx%2BWkbtfWMxE9OsfvbkAiAnKBCjPEY0LfHFHx%2B0sur8ozkRM%2Bl5C6tOvM4hi8WMamf5X5pft0EhjU6HtX3z2lhgbNv%2B%2BNoXMpIfd518E%2FcDK5nr3MsF7ZV7kvK5NyD82yVrARE3J7MhcxtTDt0e6cOunMc7V5iCsUxNN7EZHda4fRy98rtcCVA37iiV2NVVPPRM&X-Amz-Signature=92e51964cc4bfd43410b14e6d4b8a698f4ad1633a06bf0fd4db66dafb0985f10&X-Amz-SignedHeaders=host&x-amz-checksum-mode=ENABLED&x-id=GetObject)


![image.png](/images/posts/00c42230-0438-40a4-999a-22b88b52bc29.png)


按下 **Deploy** 即可部署，幾秒鐘後你的部落格就會正式上線！


![image.png](/images/posts/f795dd70-6e28-4d96-9ddb-e30e606e87e6.png)


## 下一步：個人化你的部落格


你可以在 config 檔案裡面設定你的部落格，[教學看這ㄦ](https://buroguru.zudo.cc/posts/config-guide-zh)


## ⏱ 自動更新機制


部署完成後，Buroguru 會透過 GitHub Actions **每 12 小時自動同步 Notion 資料並重新部署**，你不需要額外操作。


如果需要立即更新，也可以到 GitHub 專案的 **Actions** 分頁手動觸發 workflow。


## 🗣 有問題嗎？


如果你在部署過程中遇到任何問題，歡迎透過[這裡](https://wusandwitch.zudo.cc/)提供的聯絡方式私訊我！


如果你覺得這個專案對你有幫助，請幫我在 GitHub 上按個 ⭐️，我會非常感謝！

