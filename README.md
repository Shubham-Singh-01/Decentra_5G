# 🚀 Decentra_5G

A **next-generation 5G authentication framework** that integrates **decentralized identity (DID)** via **blockchain** and secure access management using **OAuth2**. This project leverages `Free5GC`, `Keycloak`, and smart contracts to create a robust, privacy-preserving network authentication system for modern telecom infrastructure.

## 🧠 Why Decentra_5G?

Modern mobile networks require authentication systems that are:
- Secure
- Scalable
- Privacy-respecting
- Interoperable across domains

Decentra_5G reimagines how authentication in 5G works by combining:
- ✅ OAuth2.0 for standards-based access token management  
- 🔐 Decentralized Identity via Blockchain (DID)  
- 📡 Free5GC as the core 5G network stack  

## 📐 Architecture Overview

```
 +------------+        +----------------+       +-------------------+
 |    UE      | <----> |   Free5GC AMF  | <---> |  OAuth2 Server    |
 | (User Dev) |        |     (5G Core)  |       |   (e.g., Keycloak)|
 +------------+        +----------------+       +-------------------+
                            |                            |
                            v                            v
                    +---------------+           +------------------+
                    | Blockchain    | <-------> |  Smart Contracts  |
                    | Identity/DID  |           +------------------+
                    +---------------+
```

- **UE (User Equipment)** connects to 5GC (Free5GC)
- **AMF** forwards auth requests to an OAuth2-compliant server
- **OAuth2 Server** verifies the user via blockchain-issued tokens
- **Blockchain Layer** contains DIDs and smart contracts for identity verification

## ⚙️ Technologies Used

| Component      | Tech Stack                         |
|----------------|------------------------------------|
| 5G Core        | [Free5GC](https://www.free5gc.org/) |
| Auth System    | OAuth2.0 via [Keycloak](https://www.keycloak.org/) |
| Blockchain     | Ethereum or Hyperledger Fabric     |
| DID Support    | W3C-compliant DID Methods          |
| Language       | Go, Node.js, Solidity              |
| Containerization | Docker, Docker Compose           |

## 📦 Features

- 🔐 **Decentralized Identity Authentication**
- 📲 **5G UE Registration via DID Tokens**
- 🔄 **OAuth2 Token Exchange & Validation**
- ⚡ **Secure Integration with Blockchain Smart Contracts**
- 🛡️ **Privacy-by-Design Architecture**

## 🛠️ Getting Started

### Prerequisites

- Docker & Docker Compose
- Free5GC cloned and running locally
- Node.js & Go installed
- Metamask or Ganache for local Ethereum

### Setup Instructions

1. **Clone the repository**
   ```bash
   git clone https://github.com/yourname/Decentra_5G.git
   cd Decentra_5G
   ```

2. **Start Free5GC core**
   - Follow the Free5GC Installation Guide

3. **Spin up Keycloak OAuth2 Server**
   ```bash
   cd auth-server
   docker-compose up -d
   ```

4. **Deploy Smart Contracts**
   ```bash
   cd blockchain
   npm install
   truffle migrate --network development
   ```

5. **Run Integration Service**
   ```bash
   cd integration
   go run main.go
   ```

## 🧪 Test Plan

- Simulate UE registration flow
- Validate OAuth2 token issuance
- Query smart contracts for DID validity
- Run end-to-end registration and authentication

## 📁 Project Structure

```
Decentra_5G/
│
├── auth-server/           # Keycloak Docker config
├── blockchain/            # Solidity contracts and Truffle
├── integration/           # OAuth2 ↔ Blockchain bridge service
├── docs/                  # Diagrams, architecture
└── README.md
```

## 🧩 Future Enhancements

- ✅ Integrate SSI (Self-Sovereign Identity) wallets
- 🌐 Federation support across multiple telcos
- 📈 Real-time monitoring dashboard
- 🔍 Formal threat modeling and risk mitigation

## 🤝 Contribution Guidelines

We welcome contributions, issues, and forks!
To contribute:

1. Fork the repo
2. Create your branch: `git checkout -b feature-xyz`
3. Commit your changes
4. Push and create a PR

## 📜 License

MIT License. See LICENSE file for details.

## 👤 Author

Shubham Singh  
BTech Software Engineering | [LinkedIn](https://linkedin.com/in/singh200410/)  
Built with ❤️ for Linux Foundation Mentorship

## 🌍 Acknowledgements

- [Free5GC](https://www.free5gc.org/)
- [Keycloak](https://www.keycloak.org/)
- W3C DID Spec
- Ethereum & Solidity Community
