# Thumbnail Lambda
A user is able to upload an image at any size on the site [TaskMaster FrontEnd](https://master.d2qq4uwperetqm.amplifyapp.com/), and have both the original size and a thumbnail size associated with the task in question.
When an image is uploaded to my S3 bucket, it triggers a Lambda function, which is in this repo. (That Lambda function may be written in any language.)
That function creates a 50x50 pixel thumbnail version of that image, and saves it to another S3 bucket.

## How to use
Upload the .zip file when you create a Lambda. Attach this Lambda to the origin s3 bucket

## Issues
+ I keep having issues with access key errors. I nuked my project early on, redownloaded IntelliJ, regenerated new access / secret keys multiple times; and it worked after a couple renewals. I am still unsure why this occurred.
  + Found out the root of the problem. Amazon was rotating keys at this time, which is why my stuff didn't work. Others could not create new IAM users, and keys did not work. 
+ Access to second bucket: I hate that I had to make the whole thing public, or manually make each image public. There must be a better way.
