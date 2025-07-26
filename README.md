# 🌐 Static Website Hosting on Azure Storage

## 📝 Summary

This project demonstrates how to host a **static website using Azure Blob Storage**. Azure Storage allows you to serve HTML, CSS, and JavaScript files directly via a public web endpoint by enabling the static website feature. This is ideal for simple sites, landing pages, or learning how cloud storage integrates with web hosting.

---

## 📘 Topics Covered

- Azure Storage Account creation
- Static website hosting configuration
- Uploading and managing blobs (files)
- Accessing the hosted website via public endpoint
- Resource cleanup

---

## 💡 Scenario

You are tasked with hosting a simple HTML website using Azure’s built-in **Static Website** feature. You'll:
- Create a storage account
- Enable static website hosting
- Upload HTML files (`index.html` and `error.html`)
- Access the website via the public endpoint

---

## ⚙️ Step-by-Step Guide

### 1. 📦 Create a Storage Account

1. Navigate to: `Azure Portal → Storage accounts → + Create`
2. **Basics tab**:
   - **Subscription**: Select your Azure subscription
   - **Resource group**: `az900-project4-rg` *(create if it doesn’t exist)*
   - **Storage account name**: `az900webhost` *(must be globally unique)*
   - **Region**: `UK South`
   - **Performance**: Standard
   - **Redundancy**: **Locally-redundant storage (LRS)**
3. Leave other settings as default → Click **Review + create** → **Create**

---

### 2. 🌐 Enable Static Website Hosting

1. After deployment, go to your storage account: `az900webhost`
2. In the left menu, scroll to **“Static website”** (under **Data management**)
3. Click **Enable**
4.  Set the following:
   - **Index document name**: `index.html`
   - **Error document path**: `error.html`
5. Click **Save**
6. Note the **Primary endpoint URL**, e.g.: https://az900webhost.z33.web.core.windows.net/



---

### 3. 📤 Upload to Azure Storage

1. Create two simple HTML files on your machine:   `index.html` and `error.html`
2. Go to your storage account: **`az900webhost`**
3. In the left-hand menu under **Data storage**, click **Containers**
4. Open the **`$web`** container  
   *(This container is auto-created when static website hosting is enabled)*
5. Click **Upload**
6. In the upload panel:
   - Click **Browse** and select both `index.html` and `error.html` from your local machine
   - Leave default options unchanged
   - Click **Upload**

---

### 4. 🌍 Access Your Website

1. Open your browser and visit the **Primary endpoint URL** shown after enabling static website hosting. 

2. You should see the content of your `index.html`:   

      ``` Hello Az900! ```

3. To test the **error page**:

- Try visiting a non-existent path in your browser:

  ```
  https://az900webhost.z22.web.core.windows.net/doesnotexist.html
  ```

- You should see:

  ```
  Oops!
  ```

---

### 5. 🧹 Cleanup

To avoid incurring charges:

1. Go to: **Azure Portal → Resource groups**
2. Select the resource group: `az900-project4-rg`
3. Click **Delete resource group**
4. Confirm deletion by typing the name of the group

---
