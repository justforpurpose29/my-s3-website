Project Title: AWS S3 Static Website Hosting
Overview
This project demonstrates how to host a static website (HTML, CSS) on AWS S3 without using a web server like EC2.
Prerequisites
An AWS Account.
Basic HTML/CSS files ( `index.html`, `stle.css`, `error.html` ).

### Git installed on your local machine.
Step-by-Step Hosting Process

### Bucket Creation:
Log in to AWS Management Console and navigate to S3.
Create a new bucket with a unique name.
Uncheck "Block all public access" to allow public visibility.

### Uploading Files:
Upload the local project files (index.html, style.css, error.html) to the created S3 bucket.

### Enabling Static Website Hosting:
Go to the Properties tab of the bucket.
Enable Static website hosting.
Specify index.html as the "Index document" and error.html as the "Error document".

### Configuring Bucket Policy:
GO to the Permissions tab and edit the Bucket policy.
Apply the following JSON policy to allow public read access

JSON

```json

{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Sid": "PublicReadGetObject",
            "Effect": "Allow",
            "Principal": "*",
            "Action": "s3:GetObject",
            "Resource": "arn:aws:s3:::YOUR-BUCKET-NAME/*"
        }
    ]
}

Accessing the Website:
Retrieve the Bucket website endpoint from the Properties tab.
Use this URL to access your website live.
