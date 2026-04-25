Static Website Hosting on AWS (React + Vite + Amplify)
🚀 Project Overview

This project demonstrates how to build and deploy a modern React application using Vite and host it on AWS using a fully managed, production-ready architecture.

Instead of just following commands, this README explains why each tool, service, and command is used — which is what recruiters actually care about.

🧠 What This Project Shows
Frontend development (React + Vite)
Version control with Git
Cloud deployment using AWS Amplify
CI/CD (automatic deployments on every push)
Understanding of CDN + scalable architecture
🏗️ Architecture (High-Level)
Developer → GitHub → AWS Amplify → CloudFront CDN → Users
🔹 Why this architecture?
No servers needed → lower cost & maintenance
Global CDN (CloudFront) → fast load times worldwide
Git-based deployment → industry standard workflow

AWS Amplify internally uses:

S3 → stores static files
CloudFront → delivers content globally

This allows the app to scale automatically with traffic. fileciteturn0file0

📦 Step 1: Create React App (Vite)
Command:
npm create vite@latest staticwebsite -- --template react
cd staticwebsite
npm install
npm run dev
💡 Why?
vite → fast build tool (faster than Create React App)
npm install → installs dependencies
npm run dev → starts local development server

👉 This lets you build and test your app locally before deploying.

🧪 Step 2: Initialize Git & Push to GitHub
Commands:
git init
git add .
git commit -m "first commit"
git remote add origin git@github.com:<username>/staticwebsite.git
git branch -M main
git push -u origin main
💡 Why?
git init → starts version control
git add . → stages all files
git commit → saves a snapshot of your project
git remote add origin → connects your repo to GitHub
git push → uploads your code

👉 This is required because AWS Amplify pulls your code from GitHub. fileciteturn0file0

☁️ Step 3: Deploy with AWS Amplify
What you do:
Go to Amplify Console
Click Create New App
Connect GitHub repository
Select main branch
Deploy
⚙️ What Amplify Does Behind the Scenes
🔹 Build Phase
Detects your React app
Runs build commands automatically

👉 Why? Because your source code is not optimized for production.

🔹 Hosting Phase
Uploads build files to S3
Distributes via CloudFront CDN

👉 Why?

S3 → cheap and reliable storage
CloudFront → fast global delivery
🔹 CI/CD Pipeline

Every time you run:

git push

Amplify will:

Pull new code
Build app
Deploy automatically

👉 This is called continuous deployment, a key industry skill. fileciteturn0file0

🌍 Live Deployment

After deployment, Amplify gives a URL like:

https://your-app.amplifyapp.com

👉 Your app is now publicly accessible worldwide.

💸 Cost Explanation
Typically $0.50 – $3/month depending on usage fileciteturn0file0
Why so cheap?
No servers running
Pay only for storage + requests
