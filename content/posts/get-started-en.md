---
title: "Get Started: Setup your blog in 10 minutes "
description: "Tutorial of setting up your own Buroguru."
thumbnail: "/images/posts/e5cda12f-da52-4db6-b812-6c405425f388.png"
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


	![image.png](/images/posts/634c4293-7ae6-400b-b20a-b9183aafcb7e.png)

2. Update the capabilities

	Click the new added integration, In the **Content Capabilities** section, at least toggle **Read content.**


	![image.png](/images/posts/4e9c8566-44bb-4929-a31b-c4e1da45857a.png)

3. Copy Notion token

	After creating it, you’ll see a field labeled **`Internal Integration Token`**. Copy this token, we’ll use it later.


	![image.png](/images/posts/4708e09d-ba15-42e6-bad1-f9fe2a6c8a52.png)

4. Add connection

	Go back to the Notion database you create earlier in “full page”, click the three dots in the top right, then on the bottom, click **Connections** and select the integration just added.


	![image.png](/images/posts/b7a8a17b-6599-4734-b54d-280c72e0f591.png)


	![image.png](/images/posts/bc4a3fb0-77c8-4a23-a77d-5adee993d4ca.png)

5. Copy database id

	Click **Share** button on the top right, and click **Copy Link,** and you’ll get a link like [`https://www.notion.so/wusandwitch-notes/212d51c8314480ca8d4ffa62487XXXXXX?v=212d51c8314480a89fea000cXXXXXX&source=copy_link`](https://www.notion.so/wusandwitch-notes/212d51c8314480ca8d4ffa624873e734?v=212d51c8314480a89fea000c43f4e73f) .


	![image.png](/images/posts/5401abe7-efbb-491a-a734-60e1c1f79130.png)


	And the `Database ID` will be the first id (the one before `?`), the one in the example will be  [`212d51c8314480ca8d4ffa62487XXXXXX`](https://www.notion.so/wusandwitch-notes/212d51c8314480ca8d4ffa624873e734?v=212d51c8314480a89fea000c43f4e73f)```, and keep it, we'll also use it later.


## Step 3: Setting up repository and token


Once the Notion integration is ready, you can fork the Buroguru repository to your GitHub account and deploy your blog to Vercel in just a few clicks.

1. Fork the repository

	Go to [https://github.com/WuSandWitch/Buroguru](https://github.com/WuSandWitch/Buroguru) and click **Fork.**


	![image.png](/images/posts/a53ce4bd-c98a-4e04-8c30-8e00d6f75314.png)


	Give the repository you like, like `WuSandWitch-Blog`

2. Configure Github Secrets /  Notion token

	After clone, go to **Setting**, and then **Secrets and variables**, go to **Action,** and add the “Repository Secrets”, by clicking **New repository secret.**


	![image.png](/images/posts/4ff50a30-dd2c-4bae-b3ca-403a37e34826.png)


	![image.png](/images/posts/994f514f-2424-460e-a573-880a3792067c.png)


	Now add two secret, one is `NOTION_TOKEN`, which is the Notion Integration token we just keep.


	![image.png](/images/posts/da4c4d6c-39a0-4f72-bbfd-88af1d1bc75b.png)


	And another one is `NOTION_DATABASE_ID` which is the blog database id we just keep.


	![image.png](/images/posts/89efa7da-d249-4d77-ae5c-e2f5e49acfb0.png)


## Step 4: Deploy to Vercel


With your GitHub repository ready and secrets configured, it’s time to deploy your blog to [Vercel](https://vercel.com/) and go live with your Notion-powered blog!


After logging in, click **+ Add New Project**, then select your forked repo (e.g., `WuSandWitch-Blog`).


![image.png](/images/posts/3561a1b6-f4f3-43d9-8e3c-f877e869e8d2.png)


![image.png](/images/posts/cf706471-61f6-4b47-8c51-962e333c8c36.png)


And with that, your blog should be welly deploy after you hit **Deploy. Congrats.**


![image.png](/images/posts/1e083bbe-bae0-4042-8f6d-1dbd236f07cb.png)


# Next Step


You can personalize your blog in config file, check [here](https://buroguru.zudo.cc/posts/config-guide-en).


# About Auto Updates


Once your blog is deployed, Buroguru will automatically sync content from your Notion database **every 12 hours** via GitHub Actions. The new posts will be published and redeployed without any manual steps.


If needed, you can also go to the **Actions tab in GitHub** and manually trigger the update workflow.


# So…


You can DM me if you encounter some trouble during deploy your blog. You can reach me from any contact information I’ve provided in [here](https://wusandwitch.zudo.cc/).


And please give me a little star on Github if you like it, I’ll be appreciated.

