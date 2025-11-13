# 🌐 Deploy a Static Website on AWS S3 with CloudFront (HTTPS)

This guide explains how to host and deploy a **static website** using **Amazon S3** and **CloudFront** for global distribution and HTTPS access.

---

## 🧱 1. Prerequisites
- AWS Account  
- Basic HTML/CSS website files (`index.html`, `error.html`, `style.css`)
- AWS CLI (optional, for automation)

---

## 📂 2. Create an S3 Bucket
1. Go to **AWS Console → S3 → Create bucket**
2. Bucket name:  
my-static-website-hafsa-ahamadi

3. Choose your AWS region (e.g., **us-east-1**)
4. **Uncheck** “Block all public access”
5. Acknowledge the warning and click **Create bucket**

---

## 📤 3. Upload Your Website Files
1. Open the bucket → Click **Upload**
2. Add your files:
- `index.html`
- `error.html`
- `style.css`
3. Click **Upload**

---

## 🌍 4. Make Files Public
1. Select all files → Click **Actions → Make public using ACL**
2. Confirm the change

---

## ⚙️ 5. Enable Static Website Hosting
1. Open your bucket → Go to **Properties tab**
2. Scroll to **Static website hosting**
3. Click **Edit**
4. Choose **Enable**
5. Fill in:
- **Index document:** `index.html`
- **Error document:** `error.html`
6. Click **Save changes**

🟢 Copy the **Bucket website endpoint** shown —  
e.g.,  


http://my-static-website-hafsa-ahamadi.s3-website-us-east-1.amazonaws.com


This is your public website link (HTTP).

---

## 🔒 6. Add HTTPS with CloudFront
1. Go to **AWS Console → CloudFront → Create Distribution**
2. Under **Origin domain**, select your S3 bucket (ending with `.s3.amazonaws.com`)
3. Set **Viewer protocol policy** → `Redirect HTTP to HTTPS`
4. Keep other defaults and click **Create Distribution**

Wait a few minutes until the status shows **Enabled**.

---

## 🌐 7. Access Your Secure Website
After deployment, you’ll get a CloudFront domain like:


https://d3ab4example1234.cloudfront.net

✅ That’s your secure (HTTPS) website URL.

---

## 🌍 (Optional) Add a Custom Domain
If you have your own domain:
1. Go to **Route 53** or your DNS provider
2. Create a **CNAME record**:


www.yourdomain.com
 → d3ab4example1234.cloudfront.net

3. Add an SSL certificate in **AWS Certificate Manager (ACM)**

---

## 🧹 8. Clean Up (Optional)
To avoid charges:
- Delete CloudFront distribution
- Delete S3 bucket

---

## ✅ Summary
| Component | Purpose |
|------------|----------|
| **S3** | Stores static website files |
| **CloudFront** | Delivers content via CDN & adds HTTPS |
| **ACM (optional)** | Provides free SSL certificate |
| **Route 53 (optional)** | Manages custom domain DNS |

---

### 💡 Example
Once deployed, your website is accessible via:


https://d3xyz1234abcd.cloudfront.net


---

### 🧰 Author
**Hafsa Ahamadi**  
Static Website Deployment using AWS S3 + CloudFront  
🚀 Beginner-friendly DevOps project
