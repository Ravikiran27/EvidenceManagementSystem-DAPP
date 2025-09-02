# Evidence Management System DApp

## Overview
Evidence Management System DApp is a decentralized application designed to securely manage digital evidence for law enforcement and judicial processes. Leveraging Ethereum smart contracts and IPFS storage, the system ensures transparency, immutability, and accessibility of evidence records.

## Smart Contract Details

The core smart contract (`EvidenceManagement.sol`) manages evidence records, user registration, and access permissions. All evidence uploads and queries are recorded on the Ethereum blockchain, ensuring auditability and tamper-resistance.

### Structure
- **Evidence Struct**: Stores IPFS hash, case number, location, crime description, evidence type, officer name, timestamp, and existence flag.
- **Mappings**: Evidence records by ID, user roles, user names, and registration status.
- **Events**: Emitted for evidence addition, access, and user registration.

### Main Functions
- `registerUser(name, role)`: Register a user as Police or Court. Enforces unique registration and valid roles.
- `addEvidence(evidenceId, ipfsHash, caseNumber, location, crimeDescription, evidenceType)`: Police-only function to add new evidence. Stores metadata and emits an event.
- `getEvidence(evidenceId)`: Returns evidence details for registered users and emits access event.
- `getEvidenceCount()`: Returns total number of evidence records.
- `isUserRegistered(address)`: Checks if a user is registered.
- `getUserRole(address)`, `getUserName(address)`: Returns role and name for a registered user.

### Access Control & Audit Trail
- Only registered users can interact with the contract.
- Only police officers can add evidence.
- All evidence access and addition is logged via events for auditability.

### Evidence Workflow
1. Police officer registers and uploads evidence (IPFS hash + metadata).
2. Evidence is stored on-chain and can be accessed by registered court officials.
3. All actions are logged for transparency and traceability.

## User Roles & Workflow
- **Police**: Upload evidence files, register metadata, and assign cases to court
- **Court**: View, verify, and track evidence for judicial proceedings

### Workflow
1. Police user logs in via MetaMask and uploads evidence (file + metadata)
2. File is uploaded to IPFS via Pinata; IPFS hash is stored on-chain
3. Evidence is assigned to a court official for review
4. Court user logs in, views assigned evidence, and verifies authenticity

## Security Considerations
- All transactions require MetaMask authentication and are signed by the user
- Evidence files are stored on IPFS, ensuring decentralized and tamper-proof storage
- Only authorized roles can upload or view evidence
- Contract enforces access control and audit trails

## API Integration
Pinata API is used for uploading files to IPFS. You must configure your API keys securely and never expose them in public repositories.

## Troubleshooting
- **MetaMask not connected**: Ensure MetaMask is installed and set to Sepolia testnet
- **Contract address mismatch**: Verify the deployed address matches the one in frontend JS files
- **IPFS upload issues**: Check Pinata API keys and network connectivity

## Limitations & Future Improvements
- Currently supports Sepolia testnet; mainnet deployment requires further security review
- UI/UX can be enhanced for better user experience
- Multi-file evidence and advanced search features can be added
- Integration with other decentralized storage providers (e.g., Filecoin)

## Features
- Decentralized evidence storage and retrieval
- Role-based dashboards for police and court officials
- Secure file uploads to IPFS via Pinata
- Blockchain-based evidence tracking and verification
- Integration with MetaMask for transaction signing

## Prerequisites
- MetaMask browser extension (configured for Sepolia testnet)
- Pinata account for IPFS storage
- Access to Remix IDE (https://remix.ethereum.org/)

## Technologies Used
- Solidity (Smart Contracts)
- Ethereum Sepolia Testnet
- MetaMask
- Pinata (IPFS)
- Web3.js
- HTML, CSS, JavaScript (Frontend)

## Setup Instructions

### 1. Clone the Repository
```bash
git clone https://github.com/Ravikiran27/EvidenceManagementSystem-DAPP.git
cd EvidenceManagementSystem-DAPP
```

### 2. Deploy Smart Contract
1. Open `contracts/EvidenceManagement.sol` in Remix IDE.
2. Connect MetaMask to the Sepolia testnet.
3. Compile and deploy the contract using "Injected Provider - MetaMask".
4. Copy the deployed contract address for frontend integration.

### 3. Configure Pinata
1. Register at https://pinata.cloud/ and obtain API keys.
2. Use Pinata to upload evidence files and retrieve IPFS hashes.

### 4. Update Frontend Configuration
1. Insert the deployed contract address into the relevant JS files in `public/` (e.g., `app.js`).
2. Ensure MetaMask is connected to Sepolia when accessing the dashboard.

### 5. Run the Frontend
Open `public/index.html` in your browser. Interact with the police and court dashboards as required.

## Project Structure
```
contracts/           # Solidity smart contracts
build/               # Compiled contract artifacts
migrations/           # Migration scripts
public/              # Frontend files (HTML, JS, CSS)
README.md            # Project documentation
requirements.txt     # Python dependencies (if any)
truffle-config.js    # Truffle configuration (legacy)
```

## Usage
1. Police officials can upload evidence files, which are stored on IPFS and registered on the blockchain.
2. Court officials can view and verify evidence records via the dashboard.
3. All transactions require MetaMask for authentication and signing.

## License
This project is licensed under the MIT License.
