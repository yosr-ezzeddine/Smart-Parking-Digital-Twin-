# Smart-Parking-Digital-Twin-
# 🅿️ Smart Parking Digital Twin with NiFi & FIWARE

## 📌 Project Description

This project is a simple **Digital Twin simulation of a smart parking lot**. It demonstrates how to use **Apache NiFi** to simulate parking activity (cars entering or exiting) and send updates to a **FIWARE Orion Context Broker**, which maintains the state of the parking lot in real-time. The digital twin can be queried at any time to get the current number of available and occupied spots.

---

## 🧰 Technologies Used

| Technology         | Role in Project                                                             |
|--------------------|------------------------------------------------------------------------------|
| Apache NiFi        | Simulate parking events and route data                                       |
| FIWARE Orion       | Context broker to store and update the state of the digital twin (NGSI API) |
| MongoDB            | Backend database used by Orion to store entities                            |
| Docker & Compose   | Quickly run all services in containers                                       |
| cURL / Postman     | Testing the API to retrieve the digital twin state                           |

---

## 📦 Project Structure & Workflow

```text
+-------------------+
| Apache NiFi       |
| - Generates events|
| - Processes data  |
| - Sends to Orion  |
+--------+----------+
         |
         ▼
+-------------------------+
| FIWARE Orion Context    | ← ← ← ← ← ← ← ← ← ← ← ← ← ← ← ← ← ← ← ←
| - Manages Parking Entity|       You can query with curl/Postman  |
+-----------+-------------+
            |
            ▼
       +---------+
       | MongoDB |
       +---------+

