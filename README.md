# Research Management System (RMS)

A full-stack web application for user authentication and research project management, deployed on Microsoft Azure.

![CI/CD Status](https://github.com/Aniruddh-Mallya/rms-app/actions/workflows/main_rms-express-app.yml/badge.svg)

## Live Demo

**You can view the live, deployed application here:** [[https://rms-express-app.azurewebsites.net](https://rms-express-app-cwh7arftehfnefgn.westeurope-01.azurewebsites.net/dashboard)]([https://rms-express-app.azurewebsites.net](https://rms-express-app-cwh7arftehfnefgn.westeurope-01.azurewebsites.net/dashboard))

*(Note: Please replace the URL above with your actual live application URL.)*

---

## Key Features

* **Secure User Login:** A complete authentication flow where users can log in with credentials validated against a cloud database.
* **Project Dashboard:** A protected dashboard accessible after login where users can view and add new research projects.
* **Real-time Data Management:** Projects added via the dashboard are instantly saved to the database and the project list is updated in real-time without a page refresh.

---

## Tech Stack & Architecture

This project is a complete three-tier application, demonstrating skills across the front-end, back-end, database, and cloud deployment.

| Tier | Technology | Purpose |
| :--- | :--- | :--- |
| **Front-End** | HTML5, CSS3, JavaScript (React from CDN) | Dynamic and responsive user interface for login and data management. |
| **Back-End** | Node.js, Express.js | A robust REST API server to handle business logic, user authentication, and database operations. |
| **Database** | Azure SQL | A secure, relational cloud database for storing user and project data. |
| **Cloud & Deployment** | Azure App Service, GitHub Actions | The application is hosted on Azure App Service and features a complete CI/CD pipeline with GitHub Actions for automated, secure deployments. |



---

## The Development Journey & Key Learnings

This project began as a simple test application on Azure Static Web Apps. During development, a persistent, platform-level deployment error (`Failure during content distribution`) occurred that could not be resolved through standard debugging.

Instead of being blocked, a strategic decision was made to **migrate the entire application to Azure App Service**. This involved a complete architectural refactor from a serverless function model to a unified Node.js/Express.js server. This migration provided more control and transparency, which was key to overcoming the initial roadblock.

The subsequent debugging process involved a systematic, end-to-end analysis of the full stack, including:
* Diagnosing server crashes (`502 Bad Gateway`) by analyzing the **Azure App Service Log stream**.
* Fixing runtime bugs (`500 Internal Server Error`) in the database connection and query logic.
* Resolving secure deployment authentication issues by configuring a **Service Principal with Federated Credentials**.

This project is a testament to persistent, real-world problem-solving and the ability to make pragmatic architectural decisions to ensure successful project delivery.

---

## Setup & Running Locally

To run this project on your local machine, follow these steps:

1.  **Clone the repository:**
    ```bash
    git clone [https://github.com/YOUR_USERNAME/rms-app.git](https://github.com/YOUR_USERNAME/rms-app.git)
    cd rms-app
    ```

2.  **Install dependencies:**
    ```bash
    npm install
    ```

3.  **Set up environment variables:**
    * Create a file named `.env` in the root of the project.
    * Add your database credentials to this file. The `server.js` file is already configured to read from it for local development (though Azure App Service uses Application Settings for this in production).
    ```
    DB_SERVER=your_server_name.database.windows.net
    DB_DATABASE=your_database_name
    DB_USERNAME=your_db_username
    DB_PASSWORD=your_db_password
    ```

4.  **Start the server:**
    ```bash
    npm start
    ```
    The application will be available at `http://localhost:8080`.
