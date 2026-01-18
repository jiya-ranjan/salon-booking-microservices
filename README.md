# 💇 StyleSync - Microservices-Based Salon Appointment System

A **production-style, enterprise-grade full‑stack application** built using **Spring Boot Microservices + React** that allows customers to discover salons, book services, and make online payments, while salon owners manage services, bookings, and reports.

This project is designed with **real-world architecture**, focusing on **scalability, security, and clean separation of concerns**.

---

## 🚀 Key Highlights

* 🔹 **Microservices Architecture** (loosely coupled, scalable services)
* 🔐 **Secure Authentication & Authorization** using **Keycloak + JWT**
* 💳 **Payment Integration** with **Razorpay**
* 📩 **Event‑Driven Communication** using **RabbitMQ**
* 🔔 **Real‑Time Notifications** using **WebSocket**
* 🐳 **Dockerized Services** for easy deployment
* ⚛️ **Modern Frontend** with React, Redux & Tailwind CSS
* 🔒 **Secrets & Credentials secured using Environment Variables**

---

## 🏗️ System Architecture Overview

The application follows a **microservices‑based architecture**, where each service is independently deployable and responsible for a single business capability.

### 🔧 Backend Microservices

| Service                      | Responsibility                                   |
| ---------------------------- | ------------------------------------------------ |
| **User Service**             | User registration, login, profile management     |
| **Salon Service**            | Salon creation, update, search, owner management |
| **Category Service**         | Service categories per salon                     |
| **Service Offering Service** | Individual services (haircut, spa, etc.)         |
| **Booking Service**          | Appointment booking, slots, reports              |
| **Payment Service**          | Payment order creation & payment status          |
| **Eureka Server**            | Service discovery                                |

All services communicate using **Feign Clients** and asynchronous events via **RabbitMQ**.

---

## 🔐 Authentication & Security

* **Keycloak** is used as an external Identity & Access Management (IAM) system
* JWT tokens are issued by Keycloak and validated across microservices
* Role‑based access control:

  * `CUSTOMER`
  * `SALON_OWNER`
  * `ADMIN`

> 🔒 All sensitive credentials (DB, RabbitMQ, Stripe keys) are externalized using environment variables and are **never committed to the repository**.

---

## 💻 Tech Stack

### Backend

* Java 17
* Spring Boot
* Spring Security
* Spring Cloud (Eureka, Feign)
* Hibernate / JPA
* MySQL
* RabbitMQ
* WebSocket
* Keycloak
* Docker

### Frontend

* React
* Redux
* Tailwind CSS
* Material‑UI (MUI)
* Axios
* Formik

### Payments

* Razorpay (Test Mode)

---

## 📂 Project Structure

```
salon-booking-microservices
│
├── backend
│   ├── user-service
│   ├── salon-service
│   ├── category-service
│   ├── service-offering-service
│   ├── booking-service
│   ├── payment-service
│   └── eureka-server
│
├── frontend
│   └── react-app
│
├── .gitignore
└── README.md
```

---

## ⚙️ Environment Configuration

Create a `.env` file in the project root (NOT committed):

```env
DB_USERNAME=root
DB_PASSWORD=your_password

RABBITMQ_HOST=localhost
RABBITMQ_PORT=5672
RABBITMQ_USERNAME=guest
RABBITMQ_PASSWORD=guest

EUREKA_SERVER_URL=http://localhost:8070/eureka/

STRIPE_SECRET_KEY=sk_test_xxxxx
```

---

## ▶️ Running the Application Locally

### 🔹 Prerequisites

* Java 17
* Node.js
* Docker & Docker Compose
* MySQL

### 🔹 Start Keycloak (Docker)

```bash
docker run -p 8080:8080 \
-e KC_BOOTSTRAP_ADMIN_USERNAME=admin \
-e KC_BOOTSTRAP_ADMIN_PASSWORD=admin \
quay.io/keycloak/keycloak:26.1.0 start-dev
```

Configure realms, clients, and roles in Keycloak as per project setup.

---

### 🔹 Start Backend Services

Run services in the following order:

1. Eureka Server
2. User Service
3. Salon Service
4. Category Service
5. Service Offering Service
6. Booking Service
7. Payment Service

---

### 🔹 Start Frontend

```bash
cd frontend
npm install
npm start
```

---

## 📊 Key Features

* Salon discovery by city
* Service categorization
* Slot‑based appointment booking
* Online payments
* Booking reports for salon owners
* Secure role‑based dashboards
* Real‑time booking notifications

---

## 🎯 Resume Value

This project demonstrates:

* Enterprise‑level backend design
* Secure authentication using Keycloak
* Microservices communication patterns
* Real‑world payment workflows
* Clean Git & security best practices

---

## 👩‍💻 Author

**Jiya Ranjan**
B.Tech Computer Science Engineering
Graphic Era University, Dehradun

🔗 GitHub: [https://github.com/jiya-ranjan](https://github.com/jiya-ranjan)


