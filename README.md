# 🔗 URL Shortener

A simple URL Shortener service that converts long URLs into short, shareable links and redirects users efficiently.

---

## 🚀 Overview

This project is a backend-focused system that demonstrates how large-scale services like Bitly work at a high level.

It takes a long URL as input and generates a short, unique alias that redirects back to the original URL.

---

## 🧠 Core Idea

Instead of storing and sharing long URLs, we:

1. Generate a unique short ID
2. Map it to the original URL
3. Store the mapping in a database
4. Redirect users when the short URL is accessed

---

## ⚙️ Features

* Shorten long URLs
* Redirect using short links
* Unique ID generation
* Basic collision handling
* Scalable design (conceptually)

---

## 🏗️ High Level Design

### Flow

1. User sends a long URL
2. Backend generates a short code
3. Store mapping → `(short_code → long_url)`
4. Return short URL

When accessed:

1. User hits short URL
2. Backend looks up mapping
3. Redirects to original URL

---

## 🧩 Components

### 1. API Layer

Handles incoming requests:

* Create short URL
* Redirect requests

### 2. Service Layer

Contains logic for:

* Generating unique IDs
* Validating URLs

### 3. Database

Stores mappings:

```
short_code → long_url
```

### 4. Cache (Optional but important)

* Speeds up redirection
* Reduces DB load

---

## 🔑 ID Generation Strategy

Common approaches:

* Base62 encoding (recommended)
* Hashing
* Random string generation

Example:

```
12345 → "dnh"
```

---

## ⚠️ Challenges

* Handling collisions (same short code)
* Scaling database for large traffic
* Fast redirection (low latency)
* Preventing abuse (spam links)

---

## 📈 Scalability Ideas

* Use caching (Redis)
* Load balancing
* Database sharding
* Pre-generating short codes

---

## 🛠️ Tech Stack (Example)

* Backend: Node.js 
* Database: MongoDB

---

## 📌 Future Improvements

* Analytics (click tracking)
* Expiry links
* Custom short URLs
* Rate limiting

---

## 💡 Inspiration

Inspired by systems like Bitly and TinyURL.

---

## 👨‍💻 Author

**Subham Luitel**
