# OfflineUPI — Offline Mesh-Based Payment Demo

A Spring Boot project that demonstrates how a payment can be transferred through a **simulated offline device-to-device mesh network** and later submitted to a backend when an internet-connected device becomes available.

The project focuses on three important backend concepts:

- 🔐 Secure payment data using hybrid encryption
- 🔄 Reliable duplicate handling using idempotency
- 💳 Deferred transaction settlement when connectivity is restored

> **Note:** This is an educational prototype and is not a real UPI/NPCI payment system. The mesh network is simulated in software and no real Bluetooth hardware is required.

---

## 🚀 Project Overview

The idea is to simulate a situation where a user has no internet connection but still needs to send a payment.

Instead of sending the transaction directly to the backend:

```text
Sender Device
     ↓
Offline Device
     ↓
Offline Device
     ↓
Internet-Connected Bridge Device
     ↓
Spring Boot Backend
     ↓
Transaction Settlement