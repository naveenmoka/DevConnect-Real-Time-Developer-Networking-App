# DevConnect – Real-Time Developer Networking App

![Node.js](https://img.shields.io/badge/Node.js-43853D?style=for-the-badge&logo=node.js&logoColor=white) ![Express.js](https://img.shields.io/badge/Express.js-404D59?style=for-the-badge) ![MongoDB](https://img.shields.io/badge/MongoDB-4EA94B?style=for-the-badge&logo=mongodb&logoColor=white) ![JWT](https://img.shields.io/badge/JWT-black?style=for-the-badge&logo=JSON%20web%20tokens)

> **DevTinder** is a social networking platform designed specifically for developers to connect, collaborate, and build projects together. This repository contains the **Backend RESTful API** architecture that powers the application.

##  Architecture & Features

This backend is built to handle complex relationship data and high-concurrency requests, featuring:

* **Authentication & Security:**
    * Implemented robust JWT (JSON Web Token) authentication strategy.
    * Password encryption using `bcrypt` and strict schema validation.
    * Cookie-based session management for secure user persistence.
* **Database Design (Data Modeling):**
    * Relational modeling using MongoDB (NoSQL) for User Profiles and Connection Requests.
    * Compound indexing for optimized query performance on the Feed API.
* **Core Logic:**
    * **Connection Engine:** Logic to handle 'Interested', 'Ignored', and 'Accepted' requests.
    * **Feed Algorithm:** Intelligent pagination and filtering to hide existing connections from the user feed.
    * **Sanitization:** Input validation to prevent malicious data injection.

##  Tech Stack

* **Runtime:** Node.js
* **Framework:** Express.js
* **Database:** MongoDB (via Mongoose ODM)
* **Auth:** JWT, Bcrypt, Cookie-Parser
* **Validation:** Validator.js

##  API Endpoints

| Method | Endpoint | Description |
| :--- | :--- | :--- |
| **POST** | `/signup` | Register a new developer profile |
| **POST** | `/login` | Authenticate user and issue cookie |
| **GET** | `/feed` | Fetch paginated profiles for the user feed |
| **POST** | `/request/send/:status/:userId` | Send 'interested' or 'ignored' request |
| **POST** | `/request/review/:status/:requestId` | Accept or Reject a connection request |
| **GET** | `/user/connections` | View all matched developer connections |

##  Getting Started locally

1.  **Clone the repository**
    ```bash
    git clone [https://github.com/naveenmoka/DevConnect – Real-Time Developer Networking App.git](https://github.com/naveenmoka/DevConnect-Real-Time-Developer-Networking-App).git)
    ```

2.  **Install Dependencies**
    ```bash
    cd DevTinder-Backend
    npm install
    ```

3.  **Environment Setup**
    Create a `.env` file in the root directory and add:
    ```env
    DB_CONNECTION_STRING=your_mongodb_connection_url
    JWT_SECRET=your_secret_key
    ```

4.  **Run the Server**
    ```bash
    npm run start
    ```

## Future Roadmap

* [ ] Real-time Chat integration using **Socket.io**.
* [ ] Premium membership features (Payment Gateway).
* [ ] Push Notifications.

---

*Note: This project is part of my advanced Node.js backend engineering roadmap.*
