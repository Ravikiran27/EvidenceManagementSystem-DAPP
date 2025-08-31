# 🚔 Evidence Management System using Blockchain, IPFS & Pinata

A decentralized application (dApp) that enables secure and immutable management of digital evidence using Ethereum smart contracts and IPFS. Role-based access control ensures only authorized parties like police officers and court officials can interact with the system, protecting the integrity of uploaded evidence.

---

## 📦 Tech Stack

- **Ethereum** (Smart Contracts - Solidity)
- **Truffle** (Development Framework)
- **Ganache** (Local Ethereum Blockchain)
- **MetaMask** (Wallet & Authentication)
- **IPFS** via **Pinata** (Decentralized File Storage)
- **HTML/CSS/JavaScript** (Frontend)

---

## 🔧 Setup Instructions

### ✅ Prerequisites

Install the following tools:

- [Node.js](https://nodejs.org/)
- [Truffle](https://trufflesuite.com/)
  ```bash
  npm install -g truffle
  ```
- Ganache
- MetaMask
- Pinata Account

# 1. Clone the Repository
```bash
git clone https://github.com/Niyati1206/EvidenceManagementSystem.git
cd EvidenceManagementSystem
```

# 2. Install Dependencies
```bash
npm install
```
# 3. Setup Pinata for IPFS Uploads
- Go to https://www.pinata.cloud/
- Sign up and verify your email
- Go to your API Keys dashboard
- Generate a new key and copy:
  PINATA_API_KEY
  PINATA_SECRET_API_KEY
- Create a config.js file and add your pinata key as follows:
  ```bash
  var config = {
  PINATA_API_KEY: 'add_your_key_here',
  PINATA_SECRET_API_KEY: 'add_your_secret_key_here'
  };
  ```

# 4. Start Ganache (Local Blockchain)
 - Open the Ganache app
 - Create a new workspace and add the truffle-config.js file to it
 - Note the RPC server URL (usually http://127.0.0.1:7545)

# 5. Compile and Deploy Smart Contracts
```bash
truffle compile
truffle migrate --reset
```
- Copy the contract address from the "EvidenceManagement" contract and paste it into 
1. app.js (line number 7)
2. court-dashboard.js (line number 7)
3. police-dashboard.js (line number 7)
- Also update the ABI in frontend of all three js files

# 6. Run the frontend
```bash
npx http-server ./public
```
Then open in your browser:
📍``` http://localhost:8080```

# 7. Set up metamask
- Configure the network and set up a local network
- Add atleast 2 accounts (For Police and Court) to the metamask wallet using the private key from Ganache accounts

  ---

![image](https://github.com/user-attachments/assets/6b597f55-ab4a-4303-adb2-8a33b7f78839)








  
  
  


