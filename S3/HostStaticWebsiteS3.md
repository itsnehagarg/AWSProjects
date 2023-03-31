# 🙌 How to Host a Static Website on Amazon S3

## ⚒️ In this project I will explain how you can host a static website on an Amazon S3 Bucket.

## 👩‍💻Prerequisites

- An AWS account
- A domain name (optional)

## Step 1: Create an S3 bucket

1. Log in to your AWS account and navigate to the S3 console.
2. Click the `Create bucket` button.
3. Enter a unique name for your bucket.
4. Select the region where you want to host your website.
5. Click the `Create bucket` button.

## Step 2: Configure the bucket as a static website

1. Select the newly created bucket from the S3 console.
2. Click the `Properties` tab.
3. Click the `Static website hosting` card.
4. Select the `Use this bucket to host a website` option.
5. Enter the name of your index document (e.g. index.html).
6. Optionally, enter the name of your error document (e.g. error.html).
7. Click the `Save` button.

## Step 3: Upload your website files

1. Select the bucket from the S3 console.
2. Click the `Upload` button.
3. Select the files you want to upload.
4. Click the `Upload` button.

## Step 4: Make your website files publicly accessible

1. Select the uploaded files from the S3 console.
2. Click the `Actions` button.
3. Click the `Make public` button.
4. Confirm the action.

## Step 5: Configure DNS (optional)

1. Navigate to your domain registrar's website.
2. Create a new CNAME record with the subdomain you want to use (e.g. www) and the S3 bucket website endpoint as the target.
3. Wait for the DNS changes to propagate (this can take up to 48 hours).

## Step 6: Test your website

You're done! Now you can test your website by accessing the S3 bucket website endpoint. If you have configured DNS, you can also access your website using your domain name.

### Link to my Youtube Video on How to Host a Static Website on Amazon S3:

https://www.youtube.com/watch?v=W-nqRqMUKAY
