---
title: "Get Started: Setup your blog in 10 minutes "
description: "Tutorial of setting up your own Buroguru."
thumbnail: "https://prod-files-secure.s3.us-west-2.amazonaws.com/d7df15bf-aa2b-4058-8eb8-6e3e917478e3/1eef75ea-de40-4f47-af86-8f4c7fdfe8f7/image.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Content-Sha256=UNSIGNED-PAYLOAD&X-Amz-Credential=ASIAZI2LB4664R3AVJWK%2F20260605%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20260605T035745Z&X-Amz-Expires=3600&X-Amz-Security-Token=IQoJb3JpZ2luX2VjEJv%2F%2F%2F%2F%2F%2F%2F%2F%2F%2FwEaCXVzLXdlc3QtMiJIMEYCIQCW3lIIR7Iwi3b6x2x9Qj5vF2FCzpAEjZYpB%2FiQz1QcwgIhAKO%2FOOmFw7GAWKA4r0OsjtpvviHlFM6rHdZTJA6%2FixrpKv8DCGQQABoMNjM3NDIzMTgzODA1Igx5rVhw854Gumlui%2Fsq3ANV6D4TBK%2BrDTBAK08RJSpaFZyLDKBRCJRpgAsfsk9ooldXuk5H40Drm8Jkyju0a7aUXPqBJvZCOiM3cTpyx4A6jajOQiVPmvpiPQaY84fpiV%2FfFJ8qvaQUT6MO6AWIvZRkfcl0WyK75d8%2Bn%2Fcg05LK2zdBrttLN%2BNzTMzl4dwQMzvHFi7GaqzRU1n579anMEdznnBDe4iyCe%2FiCdEZ0yl4l4hSbgq3Lm%2FAOeS1YW17vQMtjHsU8cIkA1negFzpjZi1Nl1B%2BOJiS7xG6TqNjgzGg9a9AdsQ7C97uGLVXq89S%2BLBf5JHDiTRjOgbeMyPEKfCbEUDF11RetiGaKgyBpKImXx%2Fe9V7vMthdwtkDmPLK3ZGHO9HUfjND97TJIZL%2BgN1ZD2fXaM6qnas479P5%2BnUEm5FuE1lO51gd8DzbUB1WDNDkxTPiXMoUTZrg8k51RJFaDOMRvoWYv8glHm7NuILEiKaq0IRWtDO9lX53JEXZCgqVNrlc350oQSbYP7xgZeijWumdSQybEFR528rEzmreIQVdUOoQYDC9s8b4M7CRS9%2FTO%2FeSUluRmUsdnVY0LsfE2%2Bk%2Fdf4lXzCHdK%2B2BayYmNIXp9j7ROaCWzNffAsXsS16%2FQLMj%2B2mA1gRTD7%2FojRBjqkAUVNctWLBTb%2Fj9nJgZNUyo6LoEV5HVGgLm%2BDcYpXaPtWbq8PtrdbDiNq2NmfDq0I96sMFd97ch%2FrVgNagY1p%2BkeKKcgmhLhuS4lv3j7vGXAA1n2rr%2BKy1mF0eswydYy%2FSQqssA%2BsJDWupnpnsARcAZMluGWNK9%2F8wwO5rbZWlR6lmc3BuD%2BNLA1StM1TMwoEl9tvUgqrIpLZElwEiJccMbkQyRew&X-Amz-Signature=befb336d6d5268044b232a010029931dc5c9e2e101d8e244bacdc3a6ccec60d9&X-Amz-SignedHeaders=host&x-amz-checksum-mode=ENABLED&x-id=GetObject"
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


	![image.png](/images/posts/5b191da1-4409-480b-a8f7-c7e4a875cfcb.png)

2. Update the capabilities

	Click the new added integration, In the **Content Capabilities** section, at least toggle **Read content.**


	![image.png](/images/posts/6e13f356-ddeb-4267-9367-e4698e9d2ae3.png)

3. Copy Notion token

	After creating it, you’ll see a field labeled **`Internal Integration Token`**. Copy this token, we’ll use it later.


	![image.png](/images/posts/4e2fe321-59c1-44b6-a36e-a54608c252a6.png)

4. Add connection

	Go back to the Notion database you create earlier in “full page”, click the three dots in the top right, then on the bottom, click **Connections** and select the integration just added.


	![image.png](/images/posts/5b64dc39-a724-49ee-b95a-b4dd590499a5.png)


	![image.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/d7df15bf-aa2b-4058-8eb8-6e3e917478e3/647016bd-c01a-4fee-bd4c-3ff8f7ca08fd/image.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Content-Sha256=UNSIGNED-PAYLOAD&X-Amz-Credential=ASIAZI2LB466RPDLOX7L%2F20260605%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20260605T040915Z&X-Amz-Expires=3600&X-Amz-Security-Token=IQoJb3JpZ2luX2VjEJv%2F%2F%2F%2F%2F%2F%2F%2F%2F%2FwEaCXVzLXdlc3QtMiJHMEUCIFqkCc5CPkis%2BtvQ%2B5C1unVY7mrFGOwSxNK1PZiWm2JfAiEA16fUl4ua03o4aYWJENEaPMDztiSRwl0KzexSWfFY0DQq%2FwMIZBAAGgw2Mzc0MjMxODM4MDUiDJFql0X34%2BF9dl7yqyrcAwN5Kc1QfRRWJvSN1VHEge8LvA1hjVeUeiiGFlpafokN4UFm4BlKoNyT5caW2OZzx%2F2vg7JTROgfQTZZUZ%2BPZevues4CZOmdm1tddhOSefUFbDp5fH5YULqQOtHKV%2FrhlwVz1f7QQGCVis0oOtmTByObJRxWHUfR0yscG2M3QeG%2BbLz2maR6Qls4BlIYgKIeOTuJ5rE%2BdzTfbiN%2Bi%2FZph%2FPKWezJq0huRGtEXVT7621omgGqOlLkNxmN0Cjv4dN86Yvdr7%2B53d1GdAETJuYonG9jhZJ9H10XSydpZ6cr%2FA%2FUhFDHYf%2BWl0wClfrF5%2BdKy%2Fu%2BEF11bXyGk0H80tkrx0oa%2F6HaU1etPFHiwkEiOibbBzuR0bywIJTW%2BdDGgBTVt8QOgboECvKyzwgdvGxe%2B9LglQ3v6fK8KK%2BfeM%2B93K7BAMkct%2BCg60cyctDdlMzZr%2B6hXEMSJjdeWla%2BoX%2BVheRd74CAQuPWJRLk%2B72hNszUeBZ0kb9FprP%2Fstfc50r%2FzcT0zILbbK8z0VpVTMvtjib0IaUq2%2Fj%2BD9tRIRi9ZWy6etSa7bkKhup0y6S9JIfO3RJpF%2Boqk8DGHB1%2FpZu%2FDFeSYSwx3g3MX7lxv5IarlW2NC1r0SGhZdofNg0oMID%2BiNEGOqUBGp9%2B6n0ulZToRJnVbwlqQodBE5Vx3qoLtwdy5v6DDjyDAjzKoONYY88swuL7klDX7yFRGDNFBdYSYl%2FtZRtX2qmO0TZzvJABwk1lP63DNL0vNl9j71poRGBnzqB3WCH1PhS5gtxlb%2F7tMO96oN5FGku4T9fb3u9nJmVDzhC0rLajxXjVTc92SMEPAMJaA3FWyeVSrSIcZS8U70PcAMZupq4C8%2FdI&X-Amz-Signature=7609c6bf0c3f4f3cee8de58e0a8858eb1cedb73e48d276c79ec35a7291789754&X-Amz-SignedHeaders=host&x-amz-checksum-mode=ENABLED&x-id=GetObject)

5. Copy database id

	Click **Share** button on the top right, and click **Copy Link,** and you’ll get a link like [`https://www.notion.so/wusandwitch-notes/212d51c8314480ca8d4ffa62487XXXXXX?v=212d51c8314480a89fea000cXXXXXX&source=copy_link`](https://www.notion.so/wusandwitch-notes/212d51c8314480ca8d4ffa624873e734?v=212d51c8314480a89fea000c43f4e73f) .


	![image.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/d7df15bf-aa2b-4058-8eb8-6e3e917478e3/7897c817-b6e0-4739-993b-88cec2d9454b/image.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Content-Sha256=UNSIGNED-PAYLOAD&X-Amz-Credential=ASIAZI2LB46657NLW5BU%2F20260605%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20260605T040916Z&X-Amz-Expires=3600&X-Amz-Security-Token=IQoJb3JpZ2luX2VjEJv%2F%2F%2F%2F%2F%2F%2F%2F%2F%2FwEaCXVzLXdlc3QtMiJHMEUCIQD8WPQpRDwRuzEpkUqx%2F6pY1kJaefJZDH5ELOspvOZGqwIgAmUoWDPM%2FKfnb0F12JKTfDRztuci3ayPofR6kGZceu0q%2FwMIZBAAGgw2Mzc0MjMxODM4MDUiDDDtkEVgKthoFworRircAz9QRIHPekg9p0%2Bm4AdM1oOvn7lJy6BiuPohCp4FFpIAJKhOuIOqbYgv4lAbaufAoXvo8Y5jUlPJvboEdEDE57LVb11DBQEO%2BCCmkLA77xrjPNktYeTxU0m0YDrBs0nhpu85EGzKs6sWZRNOG3Q3kom2OJtneHZUJRcXplxFVjCuy3rSeSQkWfs4Nt1Xbmxquq2qWrT9k9BQ3J2JftzGPURvi4cX9yZX%2F5%2FEP062gc23Lvz04YuMf%2FzAjSCu6TFBBmx0q%2BisP4EmdHyYideGv85OpuDPxF8myu3WOyhBZ8Ttg%2FMluil2PL7ah08US5E2jtWlCqyQIefNV%2Fsvy667VVw%2FGU229TK1C4ckY%2B3kk%2BKGuUepfWtXvNOjjrztA3%2B8HhAJUVnL9DYu5SZrJLVXHgWgC0JMTTLDUcLDuNBCbpQEfmHrGh10jd4b39jPof9NDNmrjl7te%2FIniqvim2WT9mMEDvkOXsti1xw0tA1Vzh%2F%2Fcav8VtAlFWDh4qRCkaxTMtWSY0tcIhHJYMNZ8N%2FC7FH4ETC%2B3sZ6YCDjAItLyQbv5yufi6DMGgnRcYTFlT9Vz4513w6CnPj6r7vGfTjP8G16fYJtSpjBVdH59Tff7Qd3MTij%2FPSEjoTjDfSLMID%2BiNEGOqUBJCoahtjPKICITHVUKaHEsedfb0patn8dwnTQLhwG5MAR8uE06spJCkN9UlWcLTSn1vNMPFpcaKofuWHk6t7ORrOptt7OVNoa3%2BvWmypTQ0QtcQrXaWA3joWk7WUR3k9McQUJ1fMzopmEAoyz716LOrL0XsB5qWDLXkil4EWq3sNMopXKBXK%2Bbu4GQyeQ4jyQqYFazrBfDhsUTKZ5MPlZ5t1teP%2Bh&X-Amz-Signature=9328781da4d748259360d2888d5de77b6833a8186a701dab103327710b606b45&X-Amz-SignedHeaders=host&x-amz-checksum-mode=ENABLED&x-id=GetObject)


	And the `Database ID` will be the first id (the one before `?`), the one in the example will be  [`212d51c8314480ca8d4ffa62487XXXXXX`](https://www.notion.so/wusandwitch-notes/212d51c8314480ca8d4ffa624873e734?v=212d51c8314480a89fea000c43f4e73f)```, and keep it, we'll also use it later.


## Step 3: Setting up repository and token


Once the Notion integration is ready, you can fork the Buroguru repository to your GitHub account and deploy your blog to Vercel in just a few clicks.

1. Fork the repository

	Go to [https://github.com/WuSandWitch/Buroguru](https://github.com/WuSandWitch/Buroguru) and click **Fork.**


	![image.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/d7df15bf-aa2b-4058-8eb8-6e3e917478e3/8c85c7f0-b5c5-4410-ad74-b6259b54b26c/image.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Content-Sha256=UNSIGNED-PAYLOAD&X-Amz-Credential=ASIAZI2LB466XXO5TFJE%2F20260605%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20260605T040916Z&X-Amz-Expires=3600&X-Amz-Security-Token=IQoJb3JpZ2luX2VjEJv%2F%2F%2F%2F%2F%2F%2F%2F%2F%2FwEaCXVzLXdlc3QtMiJGMEQCIGaEI9EZCtLNobf11pUkZqh0Ydbf7C4adA%2FXffA2DgnJAiBhNwn0njL5tVHrB17aLLissA72fcowZDOhNs34xc%2BSVSr%2FAwhkEAAaDDYzNzQyMzE4MzgwNSIMpddbZFCIstlcj2ERKtwDou8al%2FbOA1%2Fa%2FJBJTkQBf1Np1py3BqcA7Ay0bHQJW6%2BSqNATN0F6h63%2B8ZfamKTuoxYDeXg%2FPxkVlsgrkUAXZoXtyu1PyoaR2H6F%2BTdiHgz1ngWeRbdE%2FOOQG3alBOK%2B0%2BVeuInkFhPn8TBTgqoarlq9rDbxU4A%2F07daWGbqt%2FAueIxp3hRcL5oobir7enQMj5OgyzuJBHnfaH0244mOGISx3VGiGtuizj7XXHens0B1w2DyuWJn15JgveS1fnevoL%2BdUsgdUfK8RAyeTgtRCKCiyA6cMuHhOlc6d3PxM%2FJkm5EYfEZPPxnqmQ6YXfl5HGXLEd4iQNlUAIWU7PF4qjJFqVGGj%2BYm1zfP2Z0ZdihnZmfwg5JOQmqj%2BKySXo%2FmDz9ElWwBes9GWu3M4PY2GMERESRglY0d5wrbdr5qSfqmtxmnHuqQ%2BEdMpEeyR%2Fuw4c152J0wwgxTVpROTvlJPnmyjapGdnI3Q2Fwb03Le7zpyuhuoy6l8rsweYii5xA%2FhAt0cVIAQwqYtwlE8G1grEmkQXaYQVg%2BijgK%2FoeIiE8x1DMOGFmC6eRL69JI6a5DuTnsp4sF0D1KBZQp3ZRcO3FO%2BZIFYqzVQaAum8cf7xQx5Kqvtl7rZbpSOdQwgf%2BI0QY6pgEahdihcZv9q5Dsui09HTKGbj5UB00CSKBfKSGJqkt7ZacSvHAi5ofQvcc78BtLn6V0iQeRg%2BOcj%2FBiLtFeq5cTccLPvEIwEZJRsxSyys9WSHVwscH41VwO49yB%2BdYwkFLgntYu2k5MSZdg8YcavHnn8wH640wIRmYURr5Lxf6Oe3CHDJL1mp%2F7urOSN0BIhoHmXhXN5oIMVhds8%2Bupyeq5K7yDESyU&X-Amz-Signature=9fe42c69e2f60c992c0e5a7252db7f63bfe39a0262a28f6291b87551294fa7be&X-Amz-SignedHeaders=host&x-amz-checksum-mode=ENABLED&x-id=GetObject)


	Give the repository you like, like `WuSandWitch-Blog`

2. Configure Github Secrets /  Notion token

	After clone, go to **Setting**, and then **Secrets and variables**, go to **Action,** and add the “Repository Secrets”, by clicking **New repository secret.**


	![image.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/d7df15bf-aa2b-4058-8eb8-6e3e917478e3/afb41d59-6547-49d6-832e-9fa56c0da652/image.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Content-Sha256=UNSIGNED-PAYLOAD&X-Amz-Credential=ASIAZI2LB466WKHKDKEZ%2F20260605%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20260605T040916Z&X-Amz-Expires=3600&X-Amz-Security-Token=IQoJb3JpZ2luX2VjEJv%2F%2F%2F%2F%2F%2F%2F%2F%2F%2FwEaCXVzLXdlc3QtMiJHMEUCIAs1FASeW1lOQfpmFlAw4EK7pXq32fh22vax%2ByGiAuqGAiEAuFADhNyndz4krA09zpzCJ7Ivz4lsVeLc%2FVWLB%2FzYI7wq%2FwMIZBAAGgw2Mzc0MjMxODM4MDUiDGtbXZLBJVaVSGO5jyrcA%2F%2FJL7JPAQ1ivA70bJJz63ocKtarjgzwA%2FRJ8g4jIJvhmQ4er%2FRodUVicahedoO0S%2Bc6vAAlBreIQ8ROjVgELxxA7K7DdUafOSyo40rc%2BHoqdHv7wh1Wh6TX3NXl61OGS0RLIJwLa%2ByAwqhWAq6oriahJiaYaAZvOZrF0QhfuG0W89zHr76PbEtA8HWDUR6laQc7qMoDBkbt2D22kNwj%2BCLFVC2w6T1xUTE0gdzzyFsdycuneE2Ak%2BnxOj%2FQ0locuyhZDpHscmsgLlyWMA3wM22bsZCgeC340pLaRruYO5A2bodHHCHdkG6sBt6tX%2BSz7sVzH5GP2Fkj4c4b7SBBRZXb4s1ei6nyWaNUaoncfEkBNO%2FEj4GBfslUo9HxvZl55kNsv%2BDx39E6GGQFhHk1g0kJffkOX9gRTUbhwXNTfp73WpRaRybC9yf%2Bs7HFbtgxT8ymfX8JHpzAuze%2FMy51QW%2F2Rf1bwuj2ZjSOdZZuwIb98505VCM0OrPuUNvsD%2B2V2M9vQzmngTjyfNw69JOOAHZrU2bx4gIKMv4Lleq5y6tw75eIaO8LT3ZpmDmpFCAV9NUmT%2FBYCkRpFxY0vv1%2FP6L0U6ocjLyoEIJ%2FfPb3oJHiN4wCyVNYnCveQxRWMMz9iNEGOqUBrBQaxSU1LGQmmAYZBYQJgWRhCpp8QYBMoTC2vbFEhkd0ZvanpvL85JYGxzy8PRKdVznLejrwUUtdHwMhQENnzaEtwMO6dHFaF12PLHBalFPnYolTFLgi79gK178ic3s1Ljg17dizlgApKMOgftFd62UsNJ886jAXW%2FAOyVJyzbujY%2FpsJLsjkAz%2BfqRYCZl6WMsA9AHAiWviiAfjWE2O7DHZWAIh&X-Amz-Signature=c0b6ccd84b56d2b58e384570f187dc495bb68836253a3241b7225a45072c636b&X-Amz-SignedHeaders=host&x-amz-checksum-mode=ENABLED&x-id=GetObject)


	![image.png](/images/posts/7a0862e1-3be0-4046-b81e-c475d84a7b05.png)


	Now add two secret, one is `NOTION_TOKEN`, which is the Notion Integration token we just keep.


	![image.png](/images/posts/e480aa70-f665-4924-a386-764dba6d9f8c.png)


	And another one is `NOTION_DATABASE_ID` which is the blog database id we just keep.


	![image.png](/images/posts/1831b14a-70bd-45b4-971a-9af6eb718db6.png)


## Step 4: Deploy to Vercel


With your GitHub repository ready and secrets configured, it’s time to deploy your blog to [Vercel](https://vercel.com/) and go live with your Notion-powered blog!


After logging in, click **+ Add New Project**, then select your forked repo (e.g., `WuSandWitch-Blog`).


![image.png](/images/posts/d0a82b1c-3f1a-448b-8014-74ff846fad8e.png)


![image.png](/images/posts/d8620ab4-8493-4740-a8bf-cc0793779006.png)


And with that, your blog should be welly deploy after you hit **Deploy. Congrats.**


![image.png](/images/posts/70df3c4a-b6ee-47bb-8b16-2196944634b5.png)


# Next Step


You can personalize your blog in config file, check [here](https://buroguru.zudo.cc/posts/config-guide-en).


# About Auto Updates


Once your blog is deployed, Buroguru will automatically sync content from your Notion database **every 12 hours** via GitHub Actions. The new posts will be published and redeployed without any manual steps.


If needed, you can also go to the **Actions tab in GitHub** and manually trigger the update workflow.


# So…


You can DM me if you encounter some trouble during deploy your blog. You can reach me from any contact information I’ve provided in [here](https://wusandwitch.zudo.cc/).


And please give me a little star on Github if you like it, I’ll be appreciated.

