# DML-Chain: Decentralizing Machine Learning with Blockchain

DML-Chain introduces a novel architecture that integrates blockchain technology with federated learning to decentralize machine learning. This approach mitigates key challenges such as data centralization, privacy breaches, and biases in training datasets. By leveraging blockchain's secure, decentralized ledger and federated learning's privacy-preserving capabilities, DML-Chain enables distributed model training without requiring centralized data repositories.

## Key Features

- **Privacy-first Training:** Data remains on local devices, preserving user privacy while enabling collaborative training.
- **Blockchain Accountability:** Blockchain records ensure transparency and track participant contributions securely.
- **Smart Contract Incentives:** An incentive mechanism rewards high-quality contributions while penalizing malicious behaviors.
- **Energy Efficiency:** Implemented on a energy-efficient, quantum-secure, single-layer blockchain(Algorand) to ensure sustainability and scalability.

Read More about Algorand on https://algorand.co/

The project's proof-of-concept demonstrates the potential for a secure, privacy-preserving ecosystem that fosters collaboration in machine learning while reducing bias and maintaining accountability.

## Status

This project is currently in **active development**. Future updates will focus on optimizing blockchain integration, improving model performance, and expanding real-world applications.

## Setup and Installation

### Prerequisites

Before setting up DML-Chain, ensure you have the following installed:

- **Node.js** (v20.0 or higher)
- **npm** (v9.0 or higher)
- **Python** (v3.8 or higher)
- **Git**
- **AlgoKit CLI** (v2.0.0 or higher)
- **MongoDB** (for storing client profile information)
- **Jupyter Notebook** (for running ML model development notebooks)

### Installing AlgoKit

AlgoKit is essential for running the Algorand blockchain backend. Install it using one of the following methods:

#### Option 1: Using pip (Recommended)

```bash
pip install algokit
```

#### Option 2: Using pipx

```bash
pipx install algokit
```

#### Option 3: Using Homebrew (macOS/Linux)

```bash
brew install algorandfoundation/tap/algokit
```

#### Option 4: Using Chocolatey (Windows)

```bash
choco install algokit
```

Verify the installation:

```bash
algokit --version
```

### Project Setup

1. **Clone the repository:**

   ```bash
   git clone https://github.com/anupa-perera/DML-Chain.git
   cd DML-Chain
   ```

2. **Bootstrap the AlgoKit project:**
   ```bash
   algokit project bootstrap all
   ```

### Backend Setup (Smart Contracts)

The backend consists of Algorand smart contracts written in TEALScript.

1. **Navigate to the contracts directory:**

   ```bash
   cd projects/DML-contracts
   ```

2. **Install dependencies:**

   ```bash
   npm install
   ```

3. **Start the local Algorand network:**

   ```bash
   algokit localnet start
   ```

4. **Compile contracts and generate clients:**

   ```bash
   npm run build
   ```

5. **Run tests:**
   ```bash
   npm run test
   ```

### ML Model Setup

The ML components handle federated learning, data aggregation, and model training.

1. **Navigate to the model directory:**

   ```bash
   cd model
   ```

2. **Create a Python virtual environment:**

   ```bash
   python -m venv venv
   ```

3. **Activate the virtual environment:**

   **Windows:**

   ```bash
   venv\Scripts\activate
   ```

   **macOS/Linux:**

   ```bash
   source venv/bin/activate
   ```

4. **Install Python dependencies:**

   ```bash
   pip install -r requirements.txt
   ```

5. **Set up environment variables:**

   ```bash
   cp .env.template .env
   ```

   Configure your MongoDB connection string and other required variables in the `.env` file.

6. **Start the ML backend server:**
   ```bash
   python backend.py
   ```

The ML backend will be available at `http://localhost:5000`

### Frontend Setup

The frontend is built with React, TypeScript, and Vite.

1. **Navigate to the frontend directory:**

   ```bash
   cd projects/DML-frontend
   ```

2. **Install dependencies:**

   ```bash
   npm install
   ```

3. **Generate app clients:**

   ```bash
   npm run generate:app-clients
   ```

4. **Start the development server:**
   ```bash
   npm run dev
   ```

The frontend will be available at `http://localhost:5173`

### Running the Complete Application

From the root directory, you can build both projects:

```bash
algokit project run build
```

### Development Workflow

#### Backend Development (Smart Contracts)

- **Compile contracts:** `npm run compile-contract`
- **Generate TypeScript clients:** `npm run generate-client`
- **Run tests:** `npm run test`
- **Lint code:** `npm run lint`

#### ML Model Development

- **Start ML backend:** `python model/backend.py`
- **Run Jupyter notebooks:** `jupyter notebook` (from model directory)
- **Data splitting:** Use `model/data_splitter/data_splitter.ipynb`
- **Model training:** Use `model/base_model/fraud-detection-model.ipynb`
- **Aggregation:** Use `model/Aggregator/Aggregator.ipynb`

#### Frontend Development

- **Start dev server:** `npm run dev`
- **Build for production:** `npm run build`
- **Run tests:** `npm run test`
- **Run E2E tests:** `npm run playwright:test`

### Environment Configuration

1. **Frontend environment:**

   ```bash
   cp projects/DML-frontend/.env.template projects/DML-frontend/.env
   ```

2. **ML Model environment:**

   ```bash
   cp model/.env.template model/.env
   ```

   Configure the following variables:

   - `MONGO_CLIENT`: MongoDB connection string
   - Other ML-specific configuration variables

3. **Configure your environment variables** in the respective `.env` files as needed.

### Troubleshooting

#### Common Issues

1. **AlgoKit not found:**

   - Ensure AlgoKit is properly installed and in your PATH
   - Try reinstalling using a different method

2. **Local network issues:**

   - Stop and restart the local network: `algokit localnet stop && algokit localnet start`
   - Reset the network: `algokit localnet reset`

3. **Node version conflicts:**

   - Use Node.js v20.0 or higher
   - Consider using nvm to manage Node versions

4. **Build failures:**

   - Clear node_modules and reinstall: `rm -rf node_modules package-lock.json && npm install`
   - Ensure all dependencies are up to date

5. **Python/ML issues:**
   - Ensure Python virtual environment is activated
   - Reinstall Python dependencies: `pip install -r model/requirements.txt`
   - Check MongoDB connection string in `.env` file
   - Verify all required Python packages are installed

### Additional Resources

- [AlgoKit Documentation](https://developer.algorand.org/docs/get-started/algokit/)
- [TEALScript Documentation](https://tealscript.algo.xyz)
- [Algorand Developer Portal](https://developer.algorand.org/)
- [React Documentation](https://react.dev/)

### Contributing

This project is in active development. Please refer to the contribution guidelines when submitting pull requests or reporting issues.
