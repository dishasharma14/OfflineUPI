# OfflineUPI

OfflineUPI is a Spring Boot project that demonstrates how a payment could be transferred between devices when there is no direct internet connection.

The project uses a **simulated device-to-device mesh network**. A payment is created on one device, passed through the mesh, and eventually reaches a bridge device that can connect to the backend and settle the payment.

> This is a simulation for learning and demonstration purposes. It does not process real UPI payments.

## How it works

The basic flow is:

```text
Create Payment
      ↓
Payment Packet
      ↓
Offline Mesh Transfer
      ↓
Bridge Device
      ↓
Backend Settlement
```

The dashboard lets you create a payment and then simulate its movement through the mesh.

Each payment packet also has a **TTL (Time To Live)** so that it does not keep travelling through the network indefinitely.

## Features

* Create simulated payments
* Simulated offline mesh communication
* Gossip-based packet transfer
* Payment packet TTL
* Bridge device for settlement
* Transaction ledger
* Account balance tracking
* Activity log
* Simple web dashboard

## Tech Stack

* Java 21
* Spring Boot
* Spring Data JPA
* H2 Database
* Thymeleaf
* HTML, CSS and JavaScript
* Maven

## Running the project

Make sure Java 21 is installed.

Clone the repository:

```bash
git clone https://github.com/dishasharma14/OfflineUPI.git
cd OfflineUPI
```

On Windows, run:

```powershell
.\mvnw.cmd spring-boot:run
```

Then open:

```text
http://localhost:8080
```

The project uses an H2 in-memory database, so no separate database setup is required.

## Demo

You can test the payment flow using:

```text
Sender:   alice@demo
Receiver: bob@demo
Amount:   500
PIN:      1234
```

Then:

```text
Send Payment
      ↓
Transfer Through Mesh
      ↓
Connect & Settle
```

After settlement, the transaction and updated balances can be viewed on the dashboard.

## Project Structure

```text
OfflineUPI/
├── src/
├── .mvn/
├── pom.xml
├── mvnw
├── mvnw.cmd
└── README.md
```

## Future Improvements

Some things that could be added later:

* Real Bluetooth communication between devices
* Better security for payment packets
* Persistent offline storage
* Digital signatures
* More realistic multi-hop mesh testing

## Note

This project is a **working simulation of an offline payment concept**, built for learning and demonstration. It is not connected to the actual UPI infrastructure.
