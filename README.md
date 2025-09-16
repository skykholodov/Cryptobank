# Cryptobank

Secure, simple, and developer-friendly toolkit for building crypto finance applications.

Cryptobank is an experimental project that provides a sample web app, smart-contract integrations, and developer utilities to help you prototype wallets, token flows, and simple on-chain banking primitives.

Badges

[![License](https://img.shields.io/badge/license-MIT-brightgreen)](LICENSE)
[![Repo size](https://img.shields.io/github/repo-size/skykholodov/Cryptobank)](https://github.com/skykholodov/Cryptobank)

Highlights

- Example wallet integration (Metamask / WalletConnect)
- Token transfer and balance management examples
- Smart contract examples and Hardhat workspace
- Simple backend for off-chain bookkeeping and notifications

Table of contents

- Features
- Tech stack
- Quick start
- Running locally
- Smart contracts
- API / Backend
- Testing
- Deployment
- Contributing
- License
- Contact

Features

- On-chain token transfers with gas estimation and retries
- ERC-20 token helper utilities (approve, transfer, balance)
- Hardhat-based contracts and scripts (deploy/test)
- Frontend demo showing balances, transfers, and transaction history
- Minimal backend showcasing how to sync events and provide a history API

Tech stack

- Frontend: React + Vite (or Next.js) + Ethers.js
- Smart contracts: Solidity + Hardhat
- Backend: Node.js + Express (or Fastify)
- Database: SQLite for local demos (switchable to Postgres)
- Tools: Docker, ESLint, Prettier, GitHub Actions

Quick start

1. Clone the repo:

   git clone https://github.com/skykholodov/Cryptobank.git
   cd Cryptobank

2. Install dependencies for frontend, backend, and contracts (each has its workspace):

   # from repo root (monorepo style)
   npm install

3. Start a local Hardhat node for development:

   cd contracts
   npx hardhat node

4. Deploy contracts to local node:

   npx hardhat run --network localhost scripts/deploy.js

5. Start backend and frontend in separate terminals:

   cd ../backend
   npm start

   cd ../frontend
   npm run dev

Running locally

- Frontend runs on http://localhost:3000 (or 5173 for Vite)
- Backend runs on http://localhost:4000
- Hardhat node runs on http://localhost:8545

Smart contracts

- Contracts live in the contracts/ directory and are designed for clarity over gas optimisation.
- Use Hardhat for compilation, testing, and deployments:

  cd contracts
  npx hardhat test
  npx hardhat compile

API / Backend

- The backend provides a simple REST API for transaction history and user metadata. Example endpoints:
  - GET /api/health
  - GET /api/addresses/:address/balance
  - GET /api/addresses/:address/transactions
  - POST /api/notify (webhook sample)

Testing

- Unit tests for smart contracts: contracts/ test suite with Hardhat + Waffle/Chai
- Integration tests using a local Hardhat node + the frontend’s e2e setup (Playwright / Cypress config can be added)

Deployment

- CI: GitHub Actions workflows can build/test contracts and frontend and optionally publish a Docker image for backend.
- Production: configure environment variables for provider URLs, database, and an API key for notifications.

Contributing

Contributions are welcome — please read CONTRIBUTING.md if present. Typical flow:

- Fork the repo
- Create a feature branch
- Open a pull request with a clear description and tests where applicable

Roadmap (ideas)

- Add multi-sig wallet examples
- On-ramp/off-ramp integration (payment providers)
- Layer-2 support and gas optimisation patterns
- A library of reusable contract patterns for banking primitives

License

This project is available under the MIT License. See LICENSE for details.

Contact

- GitHub: https://github.com/skykholodov
- Twitter / X: @skykholodov
- Email: (add your email in the repo settings or README)

Acknowledgements

Inspired by open-source crypto tooling and community examples
