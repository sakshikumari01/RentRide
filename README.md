# RentRide — Vehicle Rental Management System

A full-stack vehicle rental platform built with the MERN stack (MongoDB, Express, React, Node.js). RentRide lets rental agencies manage their fleet, customers, bookings, payments, and analytics through a premium SaaS-style admin dashboard, while customers can search, book, and pay for vehicles through a polished storefront.

## Tech stack

**Frontend:** React 19, Vite, Tailwind CSS, Framer Motion, React Router DOM, React Hook Form, Axios, TanStack Query, React Icons, Chart.js

**Backend:** Node.js, Express.js, MongoDB, Mongoose, JWT, bcrypt, Cloudinary, Multer

**Security:** Helmet, express-rate-limit, CORS, express-mongo-sanitize, express-validator

## Project structure

```
rentride/
├── client/                  # React frontend
│   └── src/
│       ├── components/      # Reusable UI components (+ components/admin)
│       ├── pages/           # Route-level pages (auth, customer, admin)
│       ├── layouts/         # MainLayout, CustomerLayout, AdminLayout
│       ├── hooks/           # useDebounce, usePagination, useClickOutside
│       ├── context/         # AuthContext
│       ├── services/        # Axios API service modules
│       └── assets/
├── server/                  # Express backend
│   ├── controllers/         # Business logic per resource
│   ├── models/              # Mongoose schemas (8 collections)
│   ├── routes/               # Express routers
│   ├── middleware/          # auth, validation, error handling, upload
│   ├── config/               # db.js, cloudinary.js
│   ├── utils/                # token, pricing, cloudinary upload helpers
│   ├── seed.js                # Demo data seeder
│   └── server.js
├── docker-compose.yml
├── vercel.json
├── render.yaml
└── README.md
```

## Database collections

`Users` · `Vehicles` · `Bookings` · `Payments` · `RentalAgreements` · `Coupons` · `Reviews` · `Notifications`

## Getting started

### Prerequisites
- Node.js 18+
- MongoDB (local or Atlas)
- A Cloudinary account (free tier works) for vehicle image uploads

### 1. Install dependencies
```bash
npm run install:all
```

### 2. Configure environment variables
Copy `server/.env.example` to `server/.env` and fill in your values:
```bash
cp server/.env.example server/.env
```

### 3. Seed demo data (optional but recommended)
```bash
npm run seed
```
This creates an admin account (`admin@rentride.com` / `admin123`), a customer account (`customer@rentride.com` / `customer123`), 8 demo vehicles, and 2 coupons.

### 4. Run the app
In two terminals:
```bash
npm run dev:server   # http://localhost:5000
npm run dev:client   # http://localhost:5173
```

The Vite dev server proxies `/api` requests to the backend automatically (see `client/vite.config.js`).

## API documentation

Base URL: `/api`

| Resource | Endpoints |
|---|---|
| Auth | `POST /auth/register`, `POST /auth/login`, `GET /auth/me`, `POST /auth/forgot-password`, `POST /auth/reset-password`, `PUT /auth/profile`, `PUT /auth/change-password` |
| Vehicles | `GET /vehicles`, `GET /vehicles/featured`, `GET /vehicles/categories`, `GET /vehicles/:id`, `POST /vehicles` (admin), `PUT /vehicles/:id` (admin), `DELETE /vehicles/:id` (admin) |
| Bookings | `GET /bookings/availability`, `POST /bookings`, `GET /bookings/my-bookings`, `GET /bookings` (admin), `GET /bookings/:id`, `PUT /bookings/:id/status` (admin), `PUT /bookings/:id/cancel`, `PUT /bookings/:id/extend` |
| Payments | `POST /payments/process`, `GET /payments/my-payments`, `GET /payments` (admin), `GET /payments/:id/invoice`, `PUT /payments/:id/refund-request`, `PUT /payments/:id/refund-process` (admin) |
| Users | `GET /users` (admin), `GET /users/:id` (admin), `PUT /users/:id/status` (admin), `DELETE /users/:id` (admin), `GET /users/wishlist`, `POST /users/wishlist` |
| Reviews | `POST /reviews`, `GET /reviews/vehicle/:vehicleId`, `DELETE /reviews/:id` |
| Coupons | `POST /coupons/validate`, `GET /coupons` (admin), `POST /coupons` (admin), `PUT /coupons/:id` (admin), `DELETE /coupons/:id` (admin) |
| Notifications | `GET /notifications`, `PUT /notifications/:id/read`, `PUT /notifications/read-all`, `DELETE /notifications/:id` |
| Dashboard (admin) | `GET /dashboard/stats`, `GET /dashboard/revenue-chart`, `GET /dashboard/booking-chart`, `GET /dashboard/category-stats`, `GET /dashboard/top-vehicles` |

All protected routes require an `Authorization: Bearer <token>` header. Admin-only routes additionally require `role: "admin"` on the authenticated user.

## Core flows implemented

- **Auth:** registration, login, forgot/reset password, JWT sessions, role-based route protection (admin vs customer)
- **Fleet browsing:** search, category/price/transmission/fuel filters, sorting, pagination, wishlist
- **Booking:** date-based availability checking, automatic price calculation (base price, discounts, coupons, 18% tax), rental agreement auto-generation
- **Payments:** simulated card payment gateway, invoices, refund requests/processing
- **Admin dashboard:** live stats, revenue trend chart, booking-status chart, category breakdown, recent activity feed, top vehicles report
- **Admin management:** vehicle CRUD with multi-image Cloudinary upload, booking status management, customer activation/deactivation, coupon management

## Deployment

- **Docker:** `docker-compose up --build` runs MongoDB, the API, and the built frontend together (set `JWT_SECRET` and Cloudinary vars in a `.env` file at the project root first).
- **Vercel:** `vercel.json` is configured to build the `client` as a static site.
- **Render:** `render.yaml` defines a Node web service for the API and a static site for the client — connect your repo in the Render dashboard and set the listed environment variables.

## Testing the payment simulator

The dummy payment gateway approves any card number except ones starting with `0000`, which simulates a failed transaction so you can test both success and failure states end-to-end.

## Notes on scope ##

This repository implements the complete core platform: authentication, fleet management, search/booking/payment/cancellation/extension flows, reviews, coupons, notifications, wishlists, and an analytics-driven admin dashboard, all wired to a real MongoDB backend. Some peripheral items from a full enterprise spec (e.g. PDF invoice generation, Swagger UI, automated test suites) are intentionally left as natural next additions — see "Next steps" below.

### Suggested next steps
- Add `pdfkit`/`puppeteer`-generated PDF invoices for the existing invoice data
- Add Swagger/OpenAPI docs via `swagger-jsdoc` + `swagger-ui-express`
- Add Jest/Supertest API tests and React Testing Library component tests
- Add an ER diagram (the 8 Mongoose schemas above map directly to one)
