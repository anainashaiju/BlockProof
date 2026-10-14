# BlockProof – Blockchain-Based Document Authenticity Verification

## Project Overview

BlockProof is a decentralized application (DApp) that verifies the authenticity of digital documents using blockchain technology. It calculates a SHA-256 hash of a selected document and stores the document's name and hash on the Ethereum Sepolia test network through a Solidity smart contract.

When a document is verified, the application calculates its hash again and checks the blockchain record. If the hash matches a registered record, the document is verified. If the document has been modified or has not been registered, verification fails.

## Features

- **MetaMask Integration:** Connect your wallet to the DApp.
- **Document Registration:** Register a document's name and SHA-256 hash on the blockchain.
- **Document Verification:** Check whether a document hash exists on the blockchain.
- **Tamper Detection:** Detect changes to document content through hash comparison.
- **Blockchain Records:** View the registered document name, registering wallet address, and registration timestamp.
- **Sepolia Test Network:** Test blockchain transactions without using real ETH.
- **Responsive User Interface:** A user-friendly interface built with HTML, CSS, and JavaScript.

## Technologies Used

- Solidity – Smart contract development
- Ethereum Sepolia – Blockchain test network
- Remix IDE – Smart contract compilation and deployment
- MetaMask – Wallet connection and transaction approval
- ethers.js – Frontend-to-blockchain interaction
- HTML, CSS, and JavaScript – Frontend development
- SHA-256 – Document fingerprint generation

## Smart Contract Details

- **Contract Name:** `DocumentVerifier`
- **Network:** Ethereum Sepolia Testnet

View the contract on [Sepolia Etherscan](https://sepolia.etherscan.io/address/0xc107709b9c59B14640EB77070e1D4E55e9495ea7).

## How It Works

1. Connect your MetaMask wallet to the DApp.
2. Select a document to register.
3. The application calculates its SHA-256 hash in the browser.
4. Submit the document name and hash for registration.
5. Approve the transaction in MetaMask.
6. The smart contract records the document information on Sepolia.
7. Select the same document in the verification section.
8. The application recalculates the hash and checks the blockchain record.
9. A matching hash indicates a registered document; a changed or unregistered document produces a not-found result.

**Note:** BlockProof stores document metadata and its hash on the blockchain, not the complete document file.

## Smart Contract Functions

### `registerDocument(string _name, string _documentHash)`

Registers a document name and its SHA-256 hash on the blockchain, together with the registering wallet address and timestamp.

### `verifyDocument(string _documentHash)`

Checks whether the supplied hash has a registered record and returns the verification status and associated details.

## Smart Contract Deployment

1. Open [Remix IDE](https://remix.ethereum.org/).
2. Create a Solidity file named `DocumentVerifier.sol` and paste the smart contract code from this repository.
3. Compile the contract using a compatible Solidity compiler version (`0.8.20` or later).
4. Open the **Deploy & Run Transactions** panel.
5. Connect Remix to MetaMask using the **Injected Provider** option.
6. Select the Ethereum Sepolia test network in MetaMask.
7. Select `DocumentVerifier` and click **Deploy**.
8. Confirm the deployment transaction in MetaMask.
9. After deployment, copy the deployed contract address and use it in the frontend configuration.

## How to Run the Project

### Prerequisites

- A modern web browser
- MetaMask browser extension
- Sepolia test ETH for registration transactions
- Python installed, or another local static web server

### Steps

1. Clone or download this repository.
2. Open the project folder containing `index.html`.
3. Start a local server in that folder:

   ```bash
   python -m http.server 8000
   ```

4. Open `http://localhost:8000` in your browser.
5. Connect MetaMask and select the Sepolia test network.
6. Register or verify a document using the website.

The frontend uses ethers.js from a CDN, so an internet connection is required.

## Testing

- Register a document and verify the unchanged original file.
- Create a copy of the original and modify its contents.
- Verify the modified copy without registering it again.
- Confirm that the modified document produces a different hash and is not found in the registered records.

## Future Enhancements

- Support multiple document formats and batch verification.
- Add document history and additional verification details.
- Improve storage and management of document metadata.

## Author

Developed as an academic blockchain DApp project.

## Application Screenshots

### 1. Home Page
![BlockProof Home Page](Home%20page.png)

### 2. Document Registration and Verification
![Register and Verify Document](Register%20and%20verify%20Page.png)

### 3. How BlockProof Works
![How BlockProof Works](How%20it%20works%20page.png)

