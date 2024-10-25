
# **Crypto Price & Alert System**

### **Project Overview**

The **Crypto Price & Alert System** is a web-based application designed to allow users to monitor real-time cryptocurrency market data and set personalized alerts based on different pricing metrics. The application is targeted towards users with varying levels of membership (VIP levels) who can access specific features based on their membership level. The system integrates with major crypto market APIs (e.g., Binance, CoinMarketCap, CoinGecko) to retrieve up-to-date information and allow users to create alerts for price changes, new listings, delistings, and more.

This README provides a detailed description of the project, focusing on front-end development and the functional requirements in the form of a Software Requirements Specification (SRS) for the Front-end module.

---

### **Table of Contents**

1. [Project Objectives](#project-objectives)
2. [Features](#features)
3. [VIP Access Levels](#vip-access-levels)
4. [Technical Stack](#technical-stack)
5. [API Endpoints Overview](#api-endpoints-overview)
6. [Front-end Modules](#front-end-modules)
7. [Setup Instructions](#setup-instructions)
8. [Project Structure](#project-structure)
9. [SRS Documentation](#srs-documentation)

---

### **Project Objectives**

- **Real-Time Data**: Display real-time data for spot, future, and funding rate pricing for cryptocurrencies.
- **User-Specific Alerts**: Allow users to set personalized alerts based on various price metrics, available through a tiered VIP system.
- **Flexible Access Control**: Implement VIP levels that allow users access to specific features based on their subscription, enhancing the product’s premium appeal.
- **Intuitive UI**: Provide a user-friendly interface to view data, create alerts, and manage user profiles and VIP subscriptions.

---

### **Features**

The Crypto Price & Alert System is designed with the following key features:

- **Data Monitoring**: Real-time monitoring of cryptocurrency spot prices, future prices, and funding rates.
- **VIP-Specific Access**: Tiered access to features, depending on the user’s VIP level.
- **Price Alerts**: Create alerts based on spot/future prices, funding rates, and differences between spot and future prices.
- **Symbol Alerts**: Alerts for new listings or delistings on exchanges.
- **Advanced Indicators**: Access to custom indicators such as EMA and Bollinger Bands, available to higher-tier VIP users.
- **Secure Authentication**: User registration, login, logout, and token-based authentication, supporting JWT tokens.

---

### **VIP Access Levels**

The system implements a tiered access control for features, with four primary levels:

1. **VIP-0**: Basic access to view spot, future, and funding rate data.
2. **VIP-1**: Additional access to view Kline (candlestick) charts.
3. **VIP-2**: Includes VIP-1 features and enables users to set alerts (e.g., price differences, symbol alerts).
4. **VIP-3**: Includes all previous features and grants access to advanced indicators (e.g., EMA, Bollinger Bands).

Each endpoint in the system is gated by the VIP level, with a **403 Forbidden** response for unauthorized access.

---

### **Technical Stack**

- **Frontend**: Next.js, React, Chart.js/D3.js (for data visualization), Axios (for API requests)
- **Backend**: Go (Gin framework)
- **Database**: MongoDB
- **Authentication**: JWT-based, with cookie management for secure sessions
- **APIs**: Binance, CoinMarketCap, and CoinGecko for real-time data

---

### **API Endpoints Overview**

The API provides various endpoints to access cryptocurrency data, set alerts, and manage user accounts. Below is a high-level overview of the API endpoints:

- **Public API (`/api/v1`)**:
  - `GET /spot-future-fundingrate`: Retrieve spot, future, and funding rate data.

- **VIP-1 API (`/api/v1/vip1`)**:
  - `GET /kline`: Retrieve Kline chart data.

- **VIP-2 API (`/api/v1/vip2`)**:
  - `POST /alerts/spot-future-difference`: Set alerts for price differences.
  - `POST /alerts/symbols`: Set alerts for new or delisted symbols.
  - `POST /alerts`: General alerts (e.g., spot, future, funding rate).

- **VIP-3 API (`/api/v1/vip3`)**:
  - `POST /indicators`: Set advanced indicators (e.g., EMA, Bollinger Bands).

For more detailed specifications, please refer to the **API Documentation**.

---

### **Front-end Modules**

The Front-end team is responsible for the following modules:

1. **Dashboard**:
   - Displays real-time data on spot, future, and funding rates.
   - Provides a UI for viewing Kline data (VIP-1+ users).

2. **Alerts Management**:
   - Provides forms for setting alerts based on user’s VIP level.
   - Manages alerts for price differences, symbol listings, and advanced indicators.

3. **User Authentication & Profile**:
   - Manages user login, registration, and logout.
   - Displays user profile information and VIP level.

4. **VIP Subscription**:
   - Displays VIP benefits and pricing options.
   - Integrates payment for upgrading VIP status (if applicable).

5. **Advanced Indicators (VIP-3)**:
   - Allows users to set and view advanced indicators on their dashboard.

---

### **Setup Instructions**

Follow these instructions to set up the development environment:

1. **Clone the repository**:
   ```bash
   git clone https://github.com/dath-241/coin-price-web.git
   ```

2. **Navigate into the project directory**:
   ```bash
   cd dev_frontend
   ```

3. **Install dependencies**:
   - For Frontend (in the `/dev_frontend` directory):
     ```bash
     //This feature will be updated later
     ```
     
4. **Start the development server**:
   - For Frontend:
     ```bash
     npm run dev
     ```

---

### **Project Structure**

Below is an overview of the directory structure for the front-end and back-end modules:

```
coin-price-web/
├── Design/
│   ├── Mockups/
│   └── Usecase Diagram/
│  
├── Documents/
│   ├── System Requirement Specification/
│   ├── API Specs (Samples API for Module Backend)/
│   └── References/
│
├── Meeting Minutes/   
│    
│
└── README.md
```

---

### **SRS Documentation**

The **Software Requirements Specification (SRS)** for the front-end module includes the following sections:

1. **System Overview**: Describes the purpose and scope of the system and its modules.
2. **Functional Requirements**:
   - **Dashboard**: Requirements for displaying real-time data and Kline data.
   - **Alerts Management**: Requirements for managing alerts based on user’s VIP level.
   - **User Authentication & Profile**: Requirements for user authentication and profile management.
   - **VIP Subscription**: Requirements for managing VIP upgrades.
3. **Non-Functional Requirements**:
   - **Performance**: Expectations for response time and load handling.
   - **Security**: Specifications for data protection, token management, and session handling.
   - **Usability**: User experience guidelines and accessibility standards.
4. **User Interface Design**:
   - Wireframes and mockups for each module and screen.
   - Navigation flow for user interactions.

5. **API Integration Requirements**:
   - Outlines data flow and integration points between front-end and back-end, and external APIs.

The full SRS documentation is included in the **`/Documents/System Requirement Specification/Crypto_Market_SRS_v1.3.pdf`** file.

---

### **Contributing**

1. Fork the repository and create a new branch for your feature.
2. Commit and push your changes to your branch.
3. Submit a pull request with a description of your changes.

For more details, please refer to the **Contributing Guide**.

---

### **Contact**

For any questions or issues, please contact the project manager or reach out to the team via the project’s communication channel.

---
