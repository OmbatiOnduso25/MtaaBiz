# 🧾 MtaaBiz Functional Specification Document

## 1. Project Overview

**Project Name**: MtaaBiz  
**Type**: Mobile-friendly Sales & Inventory Management Web App  
**Target Users**: Small business owners, market vendors, student entrepreneurs in Kenya  
**Primary Goal**: Help small business operators manage stock and record sales using smartphones  
**Deployment**: Mobile-first web app (can later be wrapped into Android APK)

---

## 2. Objectives

- Digitize manual inventory & sales records  
- Track profits and stock in real-time  
- Provide sales summaries and reports  
- Offer a lightweight, data-friendly solution for micro businesses  
- Enable monetization through a tiered subscription model  

---

## 3. User Roles and Permissions

| Role         | Description                                                    |
|--------------|----------------------------------------------------------------|
| Basic User   | Can manage up to 10 products, record sales, view daily reports |
| Pro User     | Unlimited products, PDF export, weekly/monthly reports         |

---

## 4. Functional Requirements

### 4.1 User Authentication
- Register/Login via phone/email
- Secure password hashing (BCrypt)
- Session or JWT-based authentication

### 4.2 Product Management
- Add, update, and delete products
- View product inventory list

### 4.3 Sales Management
- Select product and record sale
- Automatically deduct sold quantity from stock
- Compute total sale amount

### 4.4 Reporting
- Daily sales summary
- Weekly and monthly reports (Pro)
- Export to PDF (Pro)

### 4.5 Subscription Tier Management
- Free tier (limited features)
- Pro tier (unlocked features)
- Admin can update subscription status

---

## 5. Non-Functional Requirements

| Area         | Specification                           |
|--------------|------------------------------------------|
| Performance  | Fast load on 2G/3G                       |
| Security     | Password hashing, input validation, XSS |
| Availability | 99% uptime via free-tier host            |
| Scalability  | Spring Boot REST API micro-architecture |
| Maintainability | Clean, modular codebase             |
| Localization | English (Swahili later)                  |

---

## 6. System Architecture

### 6.1 Tech Stack

| Layer     | Technology           |
|-----------|----------------------|
| Frontend  | HTML, Bootstrap, JS  |
| Backend   | Java (Spring Boot)   |
| Database  | MySQL                |
| Auth      | Session / JWT        |
| Hosting   | Railway / Render     |

---

### 6.2 Database Schema

**Users Table**  
`id`, `email`, `phone`, `passwordHash`, `isPro`, `createdAt`

**Products Table**  
`id`, `userId`, `name`, `price`, `stock`, `createdAt`

**Sales Table**  
`id`, `productId`, `quantity`, `totalPrice`, `timestamp`

---

## 7. User Interface Sketch (Wireframe)

- **Login Page**: Input for phone/email & password, login/register buttons  
- **Dashboard**: View sales summary, add product/sale, transaction history  
- **Add Product**: Form with name, price, quantity  
- **Record Sale**: Dropdown to select product, input quantity  
- **Reports Page**: Daily/weekly report view, PDF export (Pro only)  

---

## 8. Monetization Plan

| Plan | Features                                  | Price       |
|------|-------------------------------------------|-------------|
| Free | 10 products, daily reports                | Ksh 0       |
| Pro  | Unlimited products, PDF export, trends    | Ksh 50/month|

---

## 9. Deployment Plan

1. Develop and test locally on Kali Linux  
2. Deploy backend on Render or Railway  
3. Host frontend on GitHub Pages or Netlify  
4. Release MVP to pilot users for feedback  

---

## 10. Future Enhancements

- M-Pesa Daraja API integration  
- WhatsApp reporting bot  
- Offline mode with sync support  
- Credit tracking for customers  
- Multi-user support for small teams  

---

## 11. Appendices

### A. Tools Used
- IntelliJ IDEA  
- MySQL Workbench  
- Postman  
- Figma (for UI wireframes)  

### B. Glossary
- **MVP**: Minimum Viable Product  
- **Pro User**: Paid user with enhanced features  
- **Daraja**: M-Pesa developer API for payments  

---

