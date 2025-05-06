# Deploy-Static-Websites-to-AWS

# ☁️ Deploying a Static Website to AWS S3 & CloudFront

This project demonstrates how to deploy a static website using Amazon Web Services (AWS). It covers creating an S3 bucket for hosting, setting public access permissions, configuring CloudFront as a content delivery network (CDN), and accessing the site globally.

---

## 📦 Project Overview

### ✅ Technologies Used
- **AWS S3**: Static website hosting
- **AWS CloudFront**: Global content delivery
- **IAM**: Policy configuration for public access
- **HTML/CSS**: Frontend static site

---

## 🛠️ Prerequisites

- An active **AWS account**
- [Download the starter website code](https://github.com/Pascal831/Deploy-Static-Websites-to-AWS/blob/main/udacity-starter-website.zip)

---

## 🚀 Deployment Workflow

### 1. 🎯 Create S3 Bucket

- Named: `mystaticwebsite-project1`
- Enabled static website hosting
- Defined:
  - **Index document**: `index.html`
  - **Error document**: `index.html`

### 2. 📁 Upload Website Files

- Uploaded downloaded files (HTML, CSS, assets) into the S3 bucket via the **Overview** tab

### 3. 🔒 Configure Permissions

- Disabled "Block all public access"
- Added a custom **IAM Bucket Policy** to allow `public-read` access:
  ```json
  {
    "Version": "2012-10-17",
    "Statement": [
      {
        "Sid": "PublicReadGetObject",
        "Effect": "Allow",
        "Principal": "*",
        "Action": "s3:GetObject",
        "Resource": "arn:aws:s3:::mystaticwebsite-project1/*"
      }
    ]
  }
  ```

### 4. 🌐 Test the Website

Visit the static website:
**http://mystaticwebsite-project1.s3-website-us-east-1.amazonaws.com**

> ✏️ *Replaced "Travel Blog" in `index.html` with:*
> `Pascal Egbenda, Cloud DevOps Nanodegree`

---

## 🌍 Distribute via CloudFront

### 1. Create Distribution

- Origin domain: `mystaticwebsite-project1.s3.amazonaws.com`
- Origin path: `/`
- Enabled `index.html` as **Default Root Object**

### 2. Test CloudFront URL

- CDN URL:  
  **http://d312v6dtr2bli7.cloudfront.net**

- Previously accessed via:  
  `http://d312v6dtr2bli7.cloudfront.net/index.html`

---

## 🧾 Final Notes

📌 Screenshots and detailed steps are available in the [PDF documentation](https://github.com/Pascal831/Deploy-Static-Websites-to-AWS/blob/main/Deploying%20mystaticwebsite.pdf)

📁 Repository structure:
```
/website-files
|-- index.html
|-- styles.css
|-- images/
|-- ...
README.md
```

---

## 🧠 Key Takeaways

- S3 offers a scalable and cost-effective method to host static sites
- CloudFront dramatically improves performance and security
- IAM policies are essential for securing access

---

## 👨‍💻 Author

**Pascal Egbenda**  
Cybersecurity & Cloud Enthusiast  
🔗 [My GitHub](https://github.com/Pascal831)
