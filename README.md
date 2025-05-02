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
```
---

## ⚙️ Setup de l'environnement (Docker Compose)

### 🧾 Prérequis

* [Docker](https://www.docker.com/get-started)
* [Docker Compose](https://docs.docker.com/compose/)

---

### 📁 Arborescence du projet

```
.
├── docker-compose.yml
└── README.md
```

---

📄 Fichier docker-compose.yml
Le fichier docker-compose.yml est déjà fourni dans ce dépôt.

➡️ Il suffit de cloner le projet :

```bash

git clone https://github.com/yosr-ezzeddine/Smart-Parking-Digital-Twin.git
cd <nom-du-repo>
```



---

### ▶️ Lancer les services

Lance les services en exécutant la commande suivante dans le terminal à la racine du projet :

```bash
docker-compose up -d
```
Cela va automatiquement démarrer les services suivants :

- MongoDB (port 27017)

- FIWARE Orion Context Broker (port 1026)

- Apache NiFi (port 8080)



Pour vérifier que les services sont bien lancés :

```bash
docker ps
```

---

### 🌐 Accéder aux interfaces

| Service              | Adresse locale                                                 |
| -------------------- | -------------------------------------------------------------- |
| Apache NiFi          | [http://localhost:8080/nifi](http://localhost:8080/nifi)       |
| Orion Context Broker | [http://localhost:1026/version](http://localhost:1026/version) |
| MongoDB              | Accessible sur le port `27017` (pas d’interface web)           |

---

### 🧪 Tester Orion

Pour tester si Orion est bien lancé et fonctionnel, utilise la commande suivante :

```bash
curl http://localhost:1026/version
```

Tu devrais recevoir une réponse JSON contenant la version d’Orion.

---




