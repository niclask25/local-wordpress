# 🐳 Local WordPress Development with Docker

This project provides a complete local WordPress development environment using Docker Compose with **persistent local data (bind mounts)**.

---

## 📚 Table of Contents

- [🐳 Local WordPress Development with Docker](#-local-wordpress-development-with-docker)
  - [📚 Table of Contents](#-table-of-contents)
  - [📦 Features](#-features)
  - [📁 Project Structure](#-project-structure)
  - [⚙️ Prerequisites](#️-prerequisites)
  - [🚀 Getting Started](#-getting-started)
    - [1. Clone the repository](#1-clone-the-repository)
    - [2. Start the environment](#2-start-the-environment)
    - [3. Access WordPress](#3-access-wordpress)
  - [🧪 Optional: Access phpMyAdmin](#-optional-access-phpmyadmin)
  - [🛑 Stopping the Environment](#-stopping-the-environment)
  - [🔄 Restarting](#-restarting)
  - [💾 Data Persistence](#-data-persistence)
  - [🧹 Reset (WARNING: deletes all data)](#-reset-warning-deletes-all-data)

---

## 📦 Features

- WordPress (6.9.4)
- MySQL (8.4.8)
- phpMyAdmin (5.2.3)
- Persistent data stored in local folders
- Easy setup and teardown

---

## 📁 Project Structure

```
.
├── docker-compose.yml
├── db/
│   └── data/
└── wordpress/
```

- `db/data/` → MySQL database files  
- `wordpress/` → WordPress core, plugins, themes, uploads  

---

## ⚙️ Prerequisites

Install Docker:

- **Windows / macOS:** Docker Desktop  
- **Linux:** Docker Engine + Docker Compose plugin  

👉 Official installation guide: https://docs.docker.com/get-docker/

Verify installation:

```bash
docker --version
docker compose version
```

---

## 🚀 Getting Started

### 1. Clone the repository

```bash
git clone https://github.com/niclask25/local-wordpress.git
cd local-wordpress
```

---

### 2. Start the environment

```bash
docker compose up -d
```

This will start:

- MySQL database (`db`)
- WordPress (`wordpress`)
- phpMyAdmin (`phpmyadmin`)

---

### 3. Access WordPress

Open your browser:

👉 http://localhost:8080  

On first run:

1. Select language  
2. Create admin account  
3. Finish installation  

---

## 🧪 Optional: Access phpMyAdmin

Open your browser:

👉 http://localhost:8081  

---

## 🛑 Stopping the Environment

Stop and remove containers:

```bash
docker compose down
```

Stop without removing:

```bash
docker compose stop
```

---

## 🔄 Restarting

```bash
docker compose up -d
```

---

## 💾 Data Persistence

All important data is stored locally:

- WordPress → `./wordpress/`
- Database → `./db/data/`

✔ Data remains even after stopping containers  
✔ Easy backup (just copy folders)  

---

## 🧹 Reset (WARNING: deletes all data)

```bash
docker compose down -v
rm -rf db/data/*
rm -rf wordpress/*
```
