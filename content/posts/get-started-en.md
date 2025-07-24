---
title: "Get Started: Setup your blog in 10 minutes "
description: "Tutorial of setting up your own Buroguru."
thumbnail: "/images/posts/c03bffb3-af9a-4977-8752-981dadda3ec7.png"
date: "2025-06-22"
tags: ["tutorial"]
---

### [中文版本](https://buroguru.zudo.cc/posts/get-started-zh)


# If…


you don’t know what is Buroguru, please check here.


This is the quick tutorial that teach how to deploy your own Notion blog using Buroguru.


## Step 1: Setting up database


Before deploying Buroguru, you'll need to prepare a Notion database to serve as your blog’s content source. You can either clone the [template](/21ad51c831448068b621f3b5def5dd2d) or create your own with following fields.


| Field Name    | Type          | Description                                                                                 |
| ------------- | ------------- | ------------------------------------------------------------------------------------------- |
| `Title`       | Title         | The title of the post.                                                                      |
| `id`          | Text          | The id of the post, also the url-slug of the blog. (e.g. `buruguru.zudo.cc/get-started-en`. |
| `Published`   | Checkbox      | Whether to publish.                                                                         |
| `Tags`        | Multi-select  | Category tags                                                                               |
| `Date`        | Date          | Just date that indicate the time your wrote the post.                                       |
| `Description` | Text          | Brief summary of the posts shown in preview.                                                |
| `Thumbnail`   | Files & media | Thumbnail image.                                                                            |


## Step 2: Setting up Notion Integration


To allow Buroguru to access your Notion database, you need to create a Notion Integration and get the access token.

1. Create new integration

	Go to [Notion Integration](https://www.notion.so/profile/integrations) and click ‘Add Integration’, select the workspace where your database is located, and give your integration a name like ‘blog’, the logo is not required.


	![image.png](/images/posts/05f671b2-cbec-4d21-b424-699b2fa73c03.png)

2. Update the capabilities

	Click the new added integration, In the **Content Capabilities** section, at least toggle **Read content.**


	![image.png](/images/posts/9941973e-eb52-4290-ab8a-762d4c2119d2.png)

3. Copy Notion token

	After creating it, you’ll see a field labeled **`Internal Integration Token`**. Copy this token, we’ll use it later.


	![image.png](/images/posts/1c4a96f9-7eb6-46ef-966a-d89bfb1f69e7.png)

4. Add connection

	Go back to the Notion database you create earlier in “full page”, click the three dots in the top right, then on the bottom, click **Connections** and select the integration just added.


	![image.png](/images/posts/c8a24860-d041-4569-824e-f184f86b9683.png)


	![image.png](/images/posts/bd3e2b01-5e86-46c1-8329-3536f633232e.png)

5. Copy database id

	Click **Share** button on the top right, and click **Copy Link,** and you’ll get a link like [`https://www.notion.so/wusandwitch-notes/212d51c8314480ca8d4ffa62487XXXXXX?v=212d51c8314480a89fea000cXXXXXX&source=copy_link`](https://www.notion.so/wusandwitch-notes/212d51c8314480ca8d4ffa624873e734?v=212d51c8314480a89fea000c43f4e73f) .


	![image.png](/images/posts/d6def47c-5f2b-43e3-ae2d-c894b51ef753.png)


	And the `Database ID` will be the first id (the one before `?`), the one in the example will be  [`212d51c8314480ca8d4ffa62487XXXXXX`](https://www.notion.so/wusandwitch-notes/212d51c8314480ca8d4ffa624873e734?v=212d51c8314480a89fea000c43f4e73f)```, and keep it, we'll also use it later.


## Step 3: Setting up repository and token


Once the Notion integration is ready, you can fork the Buroguru repository to your GitHub account and deploy your blog to Vercel in just a few clicks.

1. Fork the repository

	Go to [https://github.com/WuSandWitch/Buroguru](https://github.com/WuSandWitch/Buroguru) and click **Fork.**


	![image.png](/images/posts/20fa2830-1211-4a2c-afd3-07dd9dcb06eb.png)


	Give the repository you like, like `WuSandWitch-Blog`

2. Configure Github Secrets /  Notion token

	After clone, go to **Setting**, and then **Secrets and variables**, go to **Action,** and add the “Repository Secrets”, by clicking **New repository secret.**


	![image.png](/images/posts/c65584c6-3dae-4196-a81a-37a6c9dfeb11.png)


	![image.png](/images/posts/8a26284b-47d4-4e7e-8a93-8b69e5c6d5f7.png)


	Now add two secret, one is `NOTION_TOKEN`, which is the Notion Integration token we just keep.


	![image.png](/images/posts/9f48f144-f39c-4e7e-a797-70b949957761.png)


	And another one is `NOTION_DATABASE_ID` which is the blog database id we just keep.


	![image.png](/images/posts/84259378-b136-4118-9986-db6dd875aae3.png)


## Step 4: Deploy to Vercel


With your GitHub repository ready and secrets configured, it’s time to deploy your blog to [Vercel](https://vercel.com/) and go live with your Notion-powered blog!


After logging in, click **+ Add New Project**, then select your forked repo (e.g., `WuSandWitch-Blog`).


![image.png](/images/posts/f8c2381b-c1a8-4951-ab1d-67bfca29f099.png)


![image.png](/images/posts/3b156dc5-932b-45b0-b2f5-39be744e9c0f.png)


And with that, your blog should be welly deploy after you hit **Deploy. Congrats.**


![image.png](/images/posts/45bdb733-1959-41d6-bc46-47a75eb980a3.png)


# Next Step


You can personalize your blog in config file, check [here](https://buroguru.zudo.cc/posts/config-guide-en).


# About Auto Updates


Once your blog is deployed, Buroguru will automatically sync content from your Notion database **every 12 hours** via GitHub Actions. The new posts will be published and redeployed without any manual steps.


If needed, you can also go to the **Actions tab in GitHub** and manually trigger the update workflow.


# So…


You can DM me if you encounter some trouble during deploy your blog. You can reach me from any contact information I’ve provided in [here](https://wusandwitch.zudo.cc/).


And please give me a little star on Github if you like it, I’ll be appreciated.

