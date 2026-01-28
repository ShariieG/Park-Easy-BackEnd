# 🚗 ParkEasy: Smart Parking Management System (Backend)

ParkEasy is a **Java-based backend system** designed to manage the full lifecycle of a parking reservation — from booking and gate entry to exit and billing.  
This backend was developed to **simulate a real-world parking ecosystem**, including automated time tracking, access control, and payment logic.

> ⚠️ **Note:** This repository represents my **backend contribution** to a team-based project. The overall system concept was developed collaboratively.

---

## 📌 Project Overview

The backend manages parking operations by:
- Validating entry and exit access
- Tracking parking duration
- Calculating parking fees
- Managing availability and expired bookings
- Handling user reports and notifications

The system was built using **pure Java** to demonstrate backend logic, object-oriented design, and time-based processing.

---

## 🛠️ My Backend Contributions

I designed and implemented the **core backend logic and system architecture**.

### 1️⃣ Dynamic Entry & Exit Logic

- **Time-Sensitive Access Control**  
  Implemented a **15-minute grace period** in `GateEntrySystem.java`, comparing the current time against the scheduled booking time.

- **Automated Billing Engine**  
  Developed billing logic in `GateExitSystem.java` using `java.time.Duration` to:
  - Calculate total parking time
  - Round usage up to the nearest hour
  - Charge a fixed rate of **$5.00 per hour**

- **Session Management**  
  Built `Booking` and `User` models to track:
  - Check-in timestamps
  - Unique **4-digit PIN codes** for secure access

---

### 2️⃣ Data & Resource Management

- **File-Based Persistence**  
  Implemented data loading in `ParkEasyApp.java` using `.txt` files to simulate database storage for:
  - Parking locations
  - Parking area maps

- **Real-Time Availability Handling**  
  Developed `checkAvailability` and `updateSpotStatus` logic to ensure:
  - Once a spot is booked, it is removed from the available pool
  - Spot status remains consistent across the system

- **Expired Booking Cleanup**  
  Created `cancelExpiredBookings` logic to automatically:
  - Release parking spots
  - Prevent underutilization if users fail to arrive on time

---

### 3️⃣ Reporting & Notifications

- **Dispute Handling System**  
  Implemented a `Report` class to manage **“Spot Taken”** scenarios, allowing the backend to reassign users to a new spot.

- **Notification System**  
  Created timestamped confirmation messages to notify users of:
  - Successful reservations
  - Booking updates

---

## 🏗️ System Architecture

The backend is organized into modular components:

| Module | Purpose |
|------|--------|
| **ParkEasyApp.java** | Main controller for registration, login, and location selection |
| **GateEntrySystem.java** | Validates PINs and manages entry timing |
| **GateExitSystem.java** | Processes exit, calculates billing, and clears sessions |
| **Models** | `User`, `Booking`, `ParkingSpot`, `Payment`, `Report` |

---

## 🌐 Live Frontend (Replit)

To demonstrate the backend in a live environment, I uploaded the Java backend code to **Replit** and used it to create a working frontend interface.  
This allowed the backend logic (booking, entry/exit validation, and billing simulation) to be tested and showcased in a live setup.
Link to the App: https://park-easy--nongisharon.replit.app
