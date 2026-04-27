# 🌐 Static Website Hosting on AWS (React + Vite + Amplify)

## 🚀 Project Overview

This project demonstrates how I built and deployed a React application using Vite and hosted it on AWS using fully managed cloud architecture.

---

## 🧠 What I did

- Building a React app using Vite
- Using Git and GitHub for version control
- Deploying applications to the cloud
- Understanding CI/CD pipelines
- Using a CDN for fast global delivery

---

## 🏗️ Architecture

```
Developer → GitHub → AWS Amplify → CloudFront CDN → Users
```

### Why This Architecture?

- ✅ No servers required (serverless)
- ✅ Scales automatically
- ✅ Fast performance using CDN
- ✅ Continuous deployment on every push

---

## 🛠️ Tech Stack

| Technology        | Purpose                  |
| ----------------- | ------------------------ |
| React (Vite)      | Frontend framework       |
| JavaScript        | Programming language     |
| Git & GitHub      | Version control          |
| AWS Amplify       | Cloud deployment & CI/CD |
| Amazon S3         | Static file storage      |
| Amazon CloudFront | CDN for global delivery  |

Note: Amazon S3 and Amazon CloudFront are automatically integrated in AWS Amplify which provides fully managed serverless hosting

---

## 📦 Project Setup

### Create React App

```bash
npm create vite@latest staticwebsite -- --template react
cd staticwebsite
npm install
npm run dev
```

**Why these commands?**

- `npm create vite@latest` → Creates a React project
- `npm install` → Installs all project dependencies
- `npm run dev` → Runs the local development server

---

## 🔁 Git Setup & Deployment

```bash
git init
git add .
git commit -m "first commit"
git remote add origin git@github.com:<your-username>/staticwebsite.git
git branch -M main
git push -u origin main

```

- Tracks all code changes over time
- Required for CI/CD integration with AWS Amplify

---

## Deploy with AWS Amplify

### Steps

1. Go to the [AWS Amplify Console](https://console.aws.amazon.com/amplify)
2. Click **"Create New App"**
3. Connect your GitHub repository
4. Select the `main` branch
5. Click **Deploy**

---

## What Happens During Deployment

### Build Phase

- Amplify detects your React app
- Runs build commands automatically

### Hosting Phase

- Files are stored in **Amazon S3**
- Content is delivered via **CloudFront CDN**

### CI/CD Pipeline

Every `git push` automatically triggers:

```
git push → Build → Deploy → Live Site Updated
```

---

## Live Website

After deployment, your app will be available at:

```
https://your-app.amplifyapp.com
```

---

## Cost Estimate

| Resource            | Estimated Cost        |
| ------------------- | --------------------- |
| AWS Amplify Hosting | ~$0.01/build minute   |
| Amazon S3 Storage   | ~$0.023/GB            |
| CloudFront CDN      | ~$0.0085/10k requests |
| **Total (typical)** | **~$0.50 – $3/month** |

> 💡 Very low cost because no servers are running 24/7.

---

## Common Issues & Fixes

| Issue            | Fix                                         |
| ---------------- | ------------------------------------------- |
| App not updating | Run `git push` to trigger a new deployment  |
| Build failed     | Check the Amplify build logs in the console |
| Blank page       | Ensure `npm run build` works locally first  |

---

## Clean Up Resources

### Why Clean Up?

To avoid unexpected AWS charges, it is recommended to delete the app and all resources created during this project.

---

### Delete the Amplify App

1. Open the [AWS Amplify Console](https://console.aws.amazon.com/amplify)
2. In the left navigation menu, select your app (`staticwebsite`)
3. Go to **App settings**
4. Click **General settings**
5. Scroll down and choose **Delete app**
6. Confirm deletion when prompted

---

### What Gets Deleted

| Resource                | Description                        |
| ----------------------- | ---------------------------------- |
| Hosted Application      | Your live website is taken offline |
| S3 Storage Bucket       | All static build files are removed |
| CloudFront Distribution | CDN configuration is deleted       |
| CI/CD Configuration     | All pipeline settings are cleared  |

> Your AWS account will no longer be billed for any of these resources after deletion.

## Author

**Vishwa Patel** — Learning Cloud Engineering, majoring in Computer Science @ CUNY Queens College  
Building hands-on AWS projects on the path to a Cloud Engineering Internship.

[![GitHub](https://img.shields.io/badge/GitHub-Follow-black?logo=github)](https://github.com/<your-username>)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-Connect-blue?logo=linkedin)](https://linkedin.com/in/<your-username>)
