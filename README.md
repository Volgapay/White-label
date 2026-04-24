# 🚀 Cloudflare White-Label Setup Guide

This guide explains how to configure your own custom domain to work with our API using Cloudflare Workers.



## 🌐 1. Requirements

- Your domain must use **Cloudflare DNS**
- The free Cloudflare plan is fully supported



## ☁️ 2. Create a Cloudflare Account

1. Sign up for a free Cloudflare account  
2. Add your domain to the Cloudflare dashboard  
3. You will be prompted to change your **Nameservers (NS)**



## 🔁 3. Update Nameservers

Go to your domain registrar (where you purchased your domain) and:

- Replace your current nameservers with the ones provided by Cloudflare

Wait for DNS propagation (can take a few minutes to a few hours).

After this step, your domain will be active on Cloudflare DNS.



## 🌍 4. Create DNS Records (Subdomains)

In your Cloudflare dashboard, create **A records (Proxied / Orange Cloud ☁️)**:

- `api.yourdomain.com`
- `checkout.yourdomain.com`

📌 You can use any IP address (example):
8.8.8.8


⚠️ This IP is only used as a placeholder for routing the Worker and does not affect functionality.



## 🧪 Example Setup

- api.yourdomain.com  
- checkout.yourdomain.com  



## ⚙️ 5. Create a Cloudflare Worker

1. Go to **Cloudflare Workers**
2. Click **Create Application**
3. Create a new Worker
4. Open the Worker code editor



## 💻 6. Add Worker Code

Paste the provided `worker.js` code into your Worker.

⚠️ IMPORTANT:

- ❌ Do NOT change the API domain inside the code  
- ✅ Only modify:
  - Wallet address (if required)
  - Custom error page URL (optional)



## 🚀 7. Deploy the Worker

Click **Deploy** to activate your Worker.



## 🔗 8. Route Your Domain to the Worker

In the Worker settings, add routes for each subdomain:


api.yourdomain.com/*
checkout.yourdomain.com/*


📌 The `*` wildcard ensures the Worker handles all API paths.



## 🎯 Final Result

After completing all steps, your custom domain will function exactly like:

api.volgapay.com


But fully white-labeled with:

- Your domain
- Your branding
- Your routing layer



## 📊 Cloudflare Free Plan Limits

- 100,000 requests per day
- Free SSL
- Global CDN
- Custom domain support



 ## 🧠 Testing

Once setup is complete, you can test your integration using the provided API documentation.


