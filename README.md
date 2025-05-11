# Anti-Piracy DApp - Movie Marketplace

A decentralized marketplace for movies built on Ethereum blockchain with Next.js, featuring content upload, purchase, and access control functionality.

## Features

- **Wallet Integration**: Connect with MetaMask or other Ethereum wallets
- **Content Upload**: Securely upload movies to IPFS via Pinata
- **Purchase System**: Buy access to content using cryptocurrency
- **Access Control**: Verify content ownership and access rights
- **Decentralized Storage**: Utilizes IPFS for content storage

## Technology Stack

- **Frontend**: Next.js 15 (App Router)
- **Styling**: Tailwind CSS
- **Blockchain**: Ethereum
- **Web3**: Ethers.js
- **Storage**: IPFS via Pinata
- **Fonts**: Geist (Vercel's font family)

## Getting Started

### Prerequisites

- Node.js (v18 or later)
- npm or yarn
- MetaMask browser extension
- Pinata account (for IPFS storage)
- Ethereum wallet with testnet ETH

### Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/suravi363/anti-piracy-dapp.git
   cd Antipiracy-dapp
   ```

2. Install dependencies:
   ```
   npm install
   # or
   yarn install
   ```

3. Create a `.env` file in the root directory with the following variables:
   ```env
   NEXT_PUBLIC_CONTRACT_ADDRESS=YOUR_DEPLOYED_CONTRACT_ADDRESS
   PINATA_JWT=YOUR_PINATA_JWT_TOKEN
   NEXT_PUBLIC_GATEWAY_URL=YOUR_PINATA_GATEWAY_URL
   ```

4. Run the development server:
   ```bash
   npm run dev
   ```

5. Open [http://localhost:3000](http://localhost:3000) in your browser.

## Smart Contract

The DApp interacts with an Ethereum smart contract with the following key functions:

- `uploadContent(string _ipfsHash, uint256 _price)`: Upload content metadata
- `buyAccess(uint256 _contentId)`: Purchase access to content
- `checkAccess(uint256 _contentId, address _user)`: Verify user access
- `contentCount()`: Get total number of uploaded contents

### Contract ABI

The contract ABI is stored in `src/app/constants/constants.js`.

## Usage

### Connect Wallet

1. Click "Connect Wallet" button
2. Approve the connection in your wallet provider

### Upload Content

1. Navigate to `/upload`
2. Select a file and set a price in ETH
3. Click "Upload" to store on IPFS
4. Confirm blockchain transaction to register content

### Purchase Content

1. On the home page, click "Buy Movie"
2. Select content to purchase
3. Confirm transaction in your wallet

### Check Access

1. Click "Check Access"
2. View your access status for specific content

## Deployment

### Smart Contract

1. Compile and deploy the smart contract to your preferred Ethereum network
2. Update `CONTRACT_ADDRESS` in `.env` and `constants.js`

### Frontend

Deploy to Vercel
Or deploy manually:

1. Build the project:
   ```bash
   npm run build
   ```

2. Deploy the output from the `.next` folder to your preferred hosting provider

## Environment Variables

| Variable | Description |
|----------|-------------|
| `NEXT_PUBLIC_CONTRACT_ADDRESS` | Deployed smart contract address |
| `PINATA_JWT` | Pinata API JWT for IPFS uploads |
| `NEXT_PUBLIC_GATEWAY_URL` | Pinata gateway URL for content access |
