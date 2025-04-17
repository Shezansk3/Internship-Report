# 🕵️ Sniffing Attack using Wireshark – Internship Task

This repository contains documentation and results from a penetration testing task performed as part of a **Cybersecurity Internship** at **Future Intern**. The focus of this task was to capture sensitive login credentials transmitted over an insecure HTTP connection using **Wireshark**.

---

## 📌 Task Overview

- **Intern Name:** Shezan Ahmad Khan
- **Internship Role:** Cybersecurity Intern  
- **Reporting Date:** April 17, 2025  
- **Task ID:** TASK 2  
- **Task Title:** Sniffing Attack using Wireshark  

---

## 🎯 Objective

To demonstrate how unencrypted credentials (username and password) submitted via an HTTP login form can be intercepted and viewed using **Wireshark**.

---

## 🧪 Test Environment

| Component        | Details                               |
|------------------|---------------------------------------|
| OS               | Windows                               |
| Target Website   | http://testphp.vulnweb.com/login.php  |
| Packet Analyzer  | Wireshark                             |
| Web Browser      | Used to simulate login                |

---

## 🛠️ Tools Used

| Tool        | Purpose                              |
|-------------|--------------------------------------|
| Wireshark   | Packet capture and analysis          |
| Web Browser | Login simulation                     |

---

## 📝 Procedure

### 1. Start Wireshark  
- Launch Wireshark and select the active network interface (Wi-Fi/Ethernet).  
- Start capturing packets.

### 2. Apply Display Filters (Optional)  
To view only relevant traffic:
- For all HTTP: `http`  
- For POST requests: `http.request.method == "POST"`

### 3. Perform Login  
- Open the browser and visit:  
  `http://testphp.vulnweb.com/login.php`  
- Use the credentials:  
  - **Username:** `admin`  
  - **Password:** `admin123`  
- Click on the **Login** button.

### 4. Stop Capture  
- Return to Wireshark and click **Stop** to end the packet capture.

### 5. Analyze HTTP POST Request  
- Locate the POST request to `/login.php`.  
- Right-click → **Follow** → **HTTP Stream**

### 6. View Captured Credentials  
- The POST body reveals login data:
- uname=admin&pass=admin123&login=login

## 📸 Captured Example

```http
POST /login.php HTTP/1.1
Host: testphp.vulnweb.com
...
Content-Type: application/x-www-form-urlencoded
Content-Length: ...

uname=admin&pass=admin123&login=login
