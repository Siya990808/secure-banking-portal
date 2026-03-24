# Secure Banking Portal

A full-stack banking web application built with a **React** frontend and **Node.js/Express** backend, connected to **MongoDB Atlas**. The project demonstrates enterprise-grade security practices, a clean RESTful API architecture, and a fully automated CI/CD pipeline.

---

## Table of Contents
- [Overview](#overview)
- [Features](#features)
- [Tech Stack](#tech-stack)
- [Security Implementation](#security-implementation)
- [CI/CD Pipeline](#cicd-pipeline)
- [Getting Started](#getting-started)
- [Project Structure](#project-structure)

---

## Overview

This banking portal was built as a final-year project for the **Information Systems 3D (INSY7314)** module at IIE Varsity College. The focus was on implementing real-world security standards in a full-stack web application — going beyond basic authentication to cover the full spectrum of web application security threats.

The system allows users to register, log in securely, and interact with payment forms — all protected by multiple layers of security controls.

---

## Features

### Authentication & User Management
- Secure user registration and login
- bcrypt password hashing with salt rounds
- Session management with secure cookie configuration
- Input validation on all form fields using RegEx patterns

### Banking Functionality
- Payment form with real-time input validation
- Account management interface
- Transaction history display

### Security
See full security implementation below.

### DevOps & CI/CD
- Automated testing pipeline on every push to main
- SonarCloud code quality analysis with coverage gates
- Docker containerisation and Newman API tests
- Auto-deployment to Render.com on pipeline success
- Health check verification post-deployment

---

## Tech Stack

| Layer | Technology |
|-------|-----------|
| Frontend | React, HTML5, CSS3 |
| Backend | Node.js, Express.js |
| Database | MongoDB Atlas |
| Security | bcrypt, Helmet.js, express-rate-limit |
| Testing | Jest, Newman (Postman CLI) |
| CI/CD | CircleCI, SonarCloud |
| Deployment | Render.com |
| Containerisation | Docker |
| Encryption | SSL/TLS (certificates included) |

---

## Security Implementation

This project implements a comprehensive, layered security model:

| Security Control | Implementation |
|-----------------|----------------|
| ✅ Password Hashing | bcrypt with salt (industry standard) |
| ✅ Input Validation | RegEx patterns on all user inputs |
| ✅ XSS Protection | Sanitised inputs, Content Security Policy |
| ✅ CSRF Protection | Anti-CSRF token implementation |
| ✅ SQL/NoSQL Injection | Parameterised queries, input sanitisation |
| ✅ DDoS Protection | Rate limiting via express-rate-limit |
| ✅ Brute Force Prevention | Login attempt rate limiting |
| ✅ Security Headers | Helmet.js (X-Frame-Options, HSTS, etc.) |
| ✅ Transport Security | SSL/TLS encryption (HTTPS) |
| ✅ Session Security | Secure, HttpOnly, SameSite cookies |
| ✅ Database Security | MongoDB Atlas with authentication |

---

## CI/CD Pipeline

The project includes a fully automated CI/CD pipeline that runs on every push to the `main` branch:

```
Push to main
    │
    ▼
┌─────────────────────┐
│   Jest Unit Tests   │  ← 25% minimum coverage gate
└─────────────────────┘
    │
    ▼
┌─────────────────────┐
│  SonarCloud Analysis│  ← Code quality gate (can block deploy)
└─────────────────────┘
    │
    ▼
┌─────────────────────┐
│  Docker Build +     │  ← Newman API tests against container
│  Newman API Tests   │
└─────────────────────┘
    │
    ▼
┌─────────────────────┐
│ Deploy to Render    │  ← Auto-deploy on all checks passing
└─────────────────────┘
    │
    ▼
┌─────────────────────┐
│   Health Check      │  ← Verifies successful deployment
└─────────────────────┘
```

---

## Getting Started

### Prerequisites
- **Node.js** v18 or higher
- **Git**
- Internet connection (for MongoDB Atlas)

### Installation

**1. Clone the repository**
```bash
git clone https://github.com/Siya990808/secure-banking-portal.git
cd secure-banking-portal
```

**2. Set up the backend**
```bash
cd server
npm install
npm run test-db    # Verify MongoDB Atlas connection
```

**3. Set up the frontend**
```bash
cd ../client
npm install
```

**4. Run the application**

Open two terminals:
```bash
# Terminal 1 — Backend
cd server
npm run dev

# Terminal 2 — Frontend
cd client
npm start
```

**5. Access the app**
- Frontend: http://localhost:3000
- Backend API: http://localhost:5000
- HTTPS: https://localhost:5001

### Available Scripts

**Backend**
```bash
npm start              # Start server
npm run dev            # Start with auto-reload (nodemon)
npm run test-db        # Test MongoDB Atlas connection
npm run security:full-scan  # Run security audit
```

**Frontend**
```bash
npm start              # Start React development server
npm run build          # Build for production
npm test               # Run Jest tests
```

---

## Project Structure

```
secure-banking-portal/
├── client/                  # React frontend
│   ├── src/
│   │   ├── components/      # Reusable UI components
│   │   ├── pages/           # Page views (Login, Register, Dashboard)
│   │   └── App.js
│   └── package.json
├── server/                  # Node.js/Express backend
│   ├── routes/              # API route handlers
│   ├── middleware/          # Security middleware
│   ├── models/              # MongoDB schemas
│   ├── config/              # Database & security config
│   └── server.js
├── certificates/            # SSL/TLS certificates
├── .circleci/               # CI/CD pipeline configuration
│   └── config.yml
├── .gitignore
├── SETUP.md
└── README.md
```

---

## Academic Context

- **Module:** Information Systems 3D (INSY7314) — NQF Level 7
- **Institution:** IIE Varsity College
- **Qualification:** Bachelor of Computer and Information Sciences in Application Development
- **Final Mark:** 93%

---

## Author

**Siyabonga Mfusi**
**Michael Bougardt**
**Jadzia Naidoo**
**Nivad Rampasad**
**Andile Nzama**
