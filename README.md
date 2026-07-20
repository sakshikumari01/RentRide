<div align="center">

# 🚗 RentRide

### Full Stack Vehicle Rental Platform

A modern full-stack vehicle rental platform that allows users to browse, book, and manage vehicle rentals with secure authentication, online payments, PDF receipts, email notifications, and WhatsApp receipt sharing.

<p align="center">
  <img src="https://img.shields.io/badge/React-Frontend-61DAFB?style=for-the-badge&logo=react" />
  <img src="https://img.shields.io/badge/Node.js-Backend-green?style=for-the-badge&logo=node.js" />
  <img src="https://img.shields.io/badge/Express.js-API-black?style=for-the-badge&logo=express" />
  <img src="https://img.shields.io/badge/MongoDB-Database-green?style=for-the-badge&logo=mongodb" />
  <img src="https://img.shields.io/badge/JWT-Authentication-blue?style=for-the-badge&logo=jsonwebtokens" />
  <img src="https://img.shields.io/badge/TailwindCSS-UI-38B2AC?style=for-the-badge&logo=tailwind-css" />
</p>

### 🚀 Live Demo

🌐 https://rent-ride-eta.vercel.app/

> ⚠️ **Note:** This is a demo project built for learning and portfolio purposes. It is not a real vehicle rental platform.

</div>

---
# 👥 Project Team 

<table>
<tr>
<td align="center">

### 👨‍💻 Manas Mishra
**Reg. No.: 12407408**

**Role:** Full Stack Developer

</td>

<td align="center">

### 👩‍💻 Sakshi Kumari
**Reg. No.: 12407689**

**Role:** Full stack developer 

</td>

<td align="center">

### 👨‍💻 Kankipati Jnana Manikanta Devi Sriram
**Reg. No.: 12407715**

**Role:** Backend Developer

</td>
</tr>
</table>

# 📑 Table of Contents

- Overview
- Features
- Tech Stack
- Screenshots
- Architecture
- Folder Structure
- Environment Variables
- Installation
- API Routes
- Project Modules
- Security Features
- Deployment
- Future Improvements
- Author

---

# 📌 Overview

RentRide is a modern full-stack vehicle rental platform developed using the MERN Stack.

The platform enables users to:

- Browse available vehicles
- Book rental vehicles
- Manage bookings
- Make online payments
- Receive PDF receipts
- Receive Email confirmations
- Receive WhatsApp booking receipts
- Admin vehicle management

The project demonstrates modern web development practices including authentication, REST APIs, MongoDB, payment workflow, cloud image uploads, PDF generation, and responsive UI.

---

# ✨ Features

## 🔐 Authentication

- JWT Authentication
- User Registration
- User Login
- Protected Routes
- Password Encryption

---

## 🚘 Vehicle Management

- Browse Vehicles
- Featured Vehicles
- Search Vehicles
- Filter by Category
- Filter by Price
- Vehicle Details
- Vehicle Images

---

## 📅 Booking System

- Book Vehicles
- Rental Duration
- Booking History
- Booking Status
- Cancel Booking

---

## 💳 Payment Module

- Payment Integration
- Booking Confirmation
- Payment Verification

---

## 📄 Receipt System

- PDF Receipt Generation
- Email Receipt
- WhatsApp Receipt
- Download Receipt

---

## 📧 Notifications

- Email Confirmation
- WhatsApp Notifications

---

## 👨‍💼 Admin Dashboard

- Manage Vehicles
- Manage Users
- View Bookings
- Dashboard Analytics

---

## 🎨 User Experience

- Modern Responsive UI
- Dark Theme
- Mobile Friendly
- Fast Navigation
- Interactive Dashboard

---

# 🛠 Tech Stack

## Frontend

- React.js
- Vite
- Tailwind CSS
- Axios
- React Router
- React Hook Form
- TanStack Query

---

## Backend

- Node.js
- Express.js

---

## Database

- MongoDB
- Mongoose

---

## Authentication

- JWT
- bcrypt

---

## Cloud Services

- Cloudinary

---

## Notifications

- Nodemailer
- Twilio WhatsApp API

---

## PDF Generation

- PDFKit

---

## Deployment

- Vercel
- Render
- MongoDB Atlas

---

# 🖼 Application Screenshots

## 🏠 Home Page

<img width="1434" height="728" alt="image" src="https://github.com/user-attachments/assets/a025b511-d9d9-4e82-b1f8-cff58497d666" />


---

## 🚗 Vehicle Listing

<img width="1449" height="704" alt="image" src="https://github.com/user-attachments/assets/0831cc48-5fa1-4a09-8cff-0dd02d828ece" />


---

## 🚘 Vehicle Details

<img width="1442" height="719" alt="image" src="https://github.com/user-attachments/assets/0c8b2d94-6447-4732-b59d-52e9680267d9" />


---

## 📅 Booking Page

<img width="1181" height="582" alt="image" src="https://github.com/user-attachments/assets/1d045383-1739-4e69-a293-9d2f64c30dab" />


---

## 💳 Payment Page

<img width="1337" height="568" alt="image" src="https://github.com/user-attachments/assets/b570b12e-4763-436f-9fb4-8eb66e561bcd" />


---

## 👤 User Dashboard

<img width="1286" height="663" alt="image" src="https://github.com/user-attachments/assets/1eac8b1c-0be0-445d-a40a-3675cb29906a" />


---



# 🏗 Architecture

```text
React Frontend
       │
       ▼
 REST API (Axios)
       │
       ▼
Express Server
       │
       ▼
MongoDB Atlas
```

---

# 📂 Folder Structure

```bash
RentRide/

├── client/
│   ├── src/
│   ├── public/
│   └── package.json
│
├── server/
│   ├── config/
│   ├── controllers/
│   ├── middleware/
│   ├── models/
│   ├── routes/
│   ├── utils/
│   ├── receipts/
│   ├── whatsapp/
│   ├── uploads/
│   └── server.js
│
├── docker-compose.yml
├── Dockerfile
├── render.yaml
├── vercel.json
└── README.md
```

---

# 🔑 Environment Variables

## Backend

```env
PORT=

NODE_ENV=

MONGO_URI=

JWT_SECRET=

CLIENT_URL=

CLOUDINARY_CLOUD_NAME=

CLOUDINARY_API_KEY=

CLOUDINARY_API_SECRET=

EMAIL_USER=

EMAIL_PASS=

TWILIO_ACCOUNT_SID=

TWILIO_AUTH_TOKEN=

TWILIO_FROM_WHATSAPP=
```

---

# ⚙️ Installation

## Clone Repository

```bash
git clone https://github.com/manash123-eng/RentRide.git
```

## Enter Folder

```bash
cd RentRide
```

## Install Backend

```bash
cd server
npm install
```

## Install Frontend

```bash
cd ../client
npm install
```

## Start Backend

```bash
cd ../server
npm start
```

## Start Frontend

```bash
cd ../client
npm run dev
```

---

# 🔌 API Routes

## Authentication

| Method | Endpoint |
|---------|----------|
| POST | /api/auth/register |
| POST | /api/auth/login |

---

## Vehicles

| Method | Endpoint |
|---------|----------|
| GET | /api/vehicles |
| GET | /api/vehicles/featured |
| GET | /api/vehicles/:id |

---

## Booking

| Method | Endpoint |
|---------|----------|
| POST | /api/bookings |
| GET | /api/bookings |
| PUT | /api/bookings/:id |

---

## Payments

| Method | Endpoint |
|---------|----------|
| POST | /api/payments |

---

## Reviews

| Method | Endpoint |
|---------|----------|
| POST | /api/reviews |
| GET | /api/reviews |

---

# 📦 Project Modules

- User Authentication
- Vehicle Management
- Booking System
- Payment Module
- Receipt Generation
- Email Notifications
- WhatsApp Notifications
- Admin Dashboard
- Cloud Image Upload
- PDF Generator

---

# 🔒 Security Features

- JWT Authentication
- Password Encryption
- Protected Routes
- Secure REST APIs
- Input Validation
- CORS Protection
- Environment Variables
- Rate Limiting

---

# 🚀 Deployment

## Frontend

Vercel

https://rent-ride-eta.vercel.app/

---

## Backend

Render

---

## Database

MongoDB Atlas

---

# 📈 Future Improvements

- Razorpay Live Payment
- Google Login
- Vehicle Owner Dashboard
- GPS Tracking
- AI Recommendation System
- Live Chat Support
- Mobile App
- Push Notifications
- Coupon System
- Multi-language Support

---

# 👨‍💻 Author

## **Sakshi Kumari**

### B.Tech CSE Student

### Full Stack Developer

GitHub:

https://github.com/sakshikumari01



---

# ⭐ Support

If you found this project helpful, please ⭐ star this repository.

Feedback and contributions are always welcome!
