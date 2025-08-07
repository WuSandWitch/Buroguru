---
title: "Get Started: Setup your blog in 10 minutes "
description: "Tutorial of setting up your own Buroguru."
thumbnail: "/images/posts/1daeec0f-6a24-46e7-8a2d-73bca5afdfb6.png"
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


	![image.png](/images/posts/29f5514a-95f5-4dda-82e6-421b575eba88.png)

2. Update the capabilities

	Click the new added integration, In the **Content Capabilities** section, at least toggle **Read content.**


	![image.png](/images/posts/10542306-9053-41ba-a900-fa9e7a0dbdfe.png)

3. Copy Notion token

	After creating it, you’ll see a field labeled **`Internal Integration Token`**. Copy this token, we’ll use it later.


	![image.png](/images/posts/444b2f80-cb5e-4ef0-95a4-33695fa98fb8.png)

4. Add connection

	Go back to the Notion database you create earlier in “full page”, click the three dots in the top right, then on the bottom, click **Connections** and select the integration just added.


	![image.png](/images/posts/497c9352-9908-4e5f-a24a-f4adabb4afa1.png)


	![image.png](/images/posts/65c1522c-2d77-44da-958a-8e94417b61f6.png)

5. Copy database id

	Click **Share** button on the top right, and click **Copy Link,** and you’ll get a link like [`https://www.notion.so/wusandwitch-notes/212d51c8314480ca8d4ffa62487XXXXXX?v=212d51c8314480a89fea000cXXXXXX&source=copy_link`](https://www.notion.so/wusandwitch-notes/212d51c8314480ca8d4ffa624873e734?v=212d51c8314480a89fea000c43f4e73f) .


	![image.png](/images/posts/e709995d-afa4-41e4-9b03-1d4f3c1693e2.png)


	And the `Database ID` will be the first id (the one before `?`), the one in the example will be  [`212d51c8314480ca8d4ffa62487XXXXXX`](https://www.notion.so/wusandwitch-notes/212d51c8314480ca8d4ffa624873e734?v=212d51c8314480a89fea000c43f4e73f)```, and keep it, we'll also use it later.


## Step 3: Setting up repository and token


Once the Notion integration is ready, you can fork the Buroguru repository to your GitHub account and deploy your blog to Vercel in just a few clicks.

1. Fork the repository

	Go to [https://github.com/WuSandWitch/Buroguru](https://github.com/WuSandWitch/Buroguru) and click **Fork.**


	![image.png](/images/posts/582ea50a-f15d-4c90-bca2-c7373ed67496.png)


	Give the repository you like, like `WuSandWitch-Blog`

2. Configure Github Secrets /  Notion token

	After clone, go to **Setting**, and then **Secrets and variables**, go to **Action,** and add the “Repository Secrets”, by clicking **New repository secret.**


	![image.png](/images/posts/34a2ddba-75ab-4085-ab22-63614467cfa4.png)


	![image.png](/images/posts/04801268-feae-4a09-8c1a-b151dcc0e9d6.png)


	Now add two secret, one is `NOTION_TOKEN`, which is the Notion Integration token we just keep.


	![image.png](/images/posts/ae6cb5ac-2386-4904-b8a5-b26fc12c4c83.png)


	And another one is `NOTION_DATABASE_ID` which is the blog database id we just keep.


	![image.png](/images/posts/b0cfff15-bf10-4533-8267-9ecc35c32d7a.png)


## Step 4: Deploy to Vercel


With your GitHub repository ready and secrets configured, it’s time to deploy your blog to [Vercel](https://vercel.com/) and go live with your Notion-powered blog!


After logging in, click **+ Add New Project**, then select your forked repo (e.g., `WuSandWitch-Blog`).


![image.png](/images/posts/02a76b09-e42b-490a-bd7b-9311c1182bd5.png)


![image.png](/images/posts/8e404f97-c016-44b1-bd83-a351abdb4e79.png)


And with that, your blog should be welly deploy after you hit **Deploy. Congrats.**


![image.png](/images/posts/b4e7d701-82cd-4045-bcc9-e68668095210.png)


# Next Step


You can personalize your blog in config file, check [here](https://buroguru.zudo.cc/posts/config-guide-en).


# About Auto Updates


Once your blog is deployed, Buroguru will automatically sync content from your Notion database **every 12 hours** via GitHub Actions. The new posts will be published and redeployed without any manual steps.


If needed, you can also go to the **Actions tab in GitHub** and manually trigger the update workflow.


# So…


You can DM me if you encounter some trouble during deploy your blog. You can reach me from any contact information I’ve provided in [here](https://wusandwitch.zudo.cc/).


And please give me a little star on Github if you like it, I’ll be appreciated.

