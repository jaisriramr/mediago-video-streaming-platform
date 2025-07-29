# 🎥 MediaGo – Scalable Cloud-Native Video Streaming Platform

MediaGo is a full-featured, microservices-based video streaming platform inspired by Netflix and Hulu. It is designed to demonstrate advanced backend architecture, secure video delivery, subscription billing, and modern frontend integration—all deployed using cloud-native practices.

---

## 🚀 Features

- 🔐 Auth0-based authentication and role-based access control (RBAC)
- 📼 FFmpeg-based video upload and multi-resolution HLS streaming
- ☁️ AWS S3 + CloudFront for secure content storage and delivery
- 💳 Subscription engine with Stripe/Razorpay integration
- 📃 Playlist management with user-customized collections
- 👤 User profile, preferences, and playback history
- 🧱 Modular microservices architecture with Docker + Kubernetes
- 📊 Monitoring with Prometheus, Grafana, and ELK stack

---

## 🧰 Tech Stack

| Layer                | Tools                                |
| -------------------- | ------------------------------------ |
| **Frontend**         | React, HLS.js                        |
| **Backend**          | Java 17, Spring Boot (Microservices) |
| **Auth**             | Auth0                                |
| **Video Processing** | FFmpeg                               |
| **Storage**          | AWS S3 + CloudFront                  |
| **Databases**        | PostgreSQL, MongoDB, Redis           |
| **Messaging**        | Kafka / RabbitMQ                     |
| **DevOps**           | Docker, Kubernetes, GitHub Actions   |
| **Monitoring**       | Prometheus, Grafana, ELK Stack       |

---

## 🧩 Microservices

| Service                   | Description                                           |
| ------------------------- | ----------------------------------------------------- |
| `auth-service`            | Auth0 integration, JWT validation, RBAC enforcement   |
| `user-service`            | User profiles, preferences, watch history             |
| `content-service`         | Metadata for shows/movies (title, tags, genres, etc.) |
| `video-uploader-service`  | Handles upload + FFmpeg processing to S3              |
| `video-streaming-service` | Secure streaming via signed HLS URLs                  |
| `playlist-service`        | Create and manage user playlists                      |
| `subscription-service`    | Manage plan subscriptions and access logic            |
| `payment-service`         | Stripe/Razorpay integration, webhook processing       |

---

## 🧱 High-Level Design (HLD)

Each service follows domain-driven design principles and communicates via REST or message queues.

### 📚 Service HLDs

| Service              | HLD Doc                                                                      |
| -------------------- | ---------------------------------------------------------------------------- |
| Auth Service         | [`docs/hld/auth-service.md`](docs/hld/auth-service.md)                       |
| User Service         | [`docs/hld/user-service.md`](docs/hld/user-service.md)                       |
| Content Service      | [`docs/hld/content-service.md`](docs/hld/content-service.md)                 |
| Playlist Service     | [`docs/hld/playlist-service.md`](docs/hld/playlist-service.md)               |
| Video Uploader       | [`docs/hld/video-uploader-service.md`](docs/hld/video-uploader-service.md)   |
| Streaming Service    | [`docs/hld/video-streaming-service.md`](docs/hld/video-streaming-service.md) |
| Subscription Service | [`docs/hld/subscription-service.md`](docs/hld/subscription-service.md)       |
| Payment Service      | [`docs/hld/payment-service.md`](docs/hld/payment-service.md)                 |

> 📁 Each file contains functional and non-functional requirements, architecture diagrams, DB schema, and API definitions.

---

## 🛠️ Project Setup

### 🔧 Prerequisites

- Docker
- Java 21
- AWS Account
- Auth0 Tenant
- PostgreSQL & MongoDB running locally or in Docker

### 📦 Clone & Run

```bash
git clone https://github.com/your-username/mediago-platform.git
cd mediago-platform
docker-compose up -d
```
