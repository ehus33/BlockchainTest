```markdown
# PetrovicCoin Blockchain

PetrovicCoin is a simple blockchain-based cryptocurrency implemented in Python using Flask. It is named in honor of Dražen Petrović, the legendary basketball player known as the "Mozart of Basketball."

## Table of Contents
- [Introduction](#introduction)
- [Features](#features)
- [Installation](#installation)
- [Usage](#usage)
  - [Running the Server](#running-the-server)
  - [Interacting with the Blockchain](#interacting-with-the-blockchain)
- [Endpoints](#endpoints)
- [Troubleshooting](#troubleshooting)
- [Acknowledgments](#acknowledgments)

## Introduction
PetrovicCoin is a minimalistic blockchain project designed to help understand the core concepts of blockchain technology. This project includes basic functionality such as creating a blockchain, mining new blocks, and processing transactions.

## Features
- **Blockchain creation**: Generate a simple blockchain with blocks that can store transactions.
- **Mining**: Implement a Proof of Work (PoW) system to mine new blocks.
- **Transactions**: Handle simple transactions between users.
- **Flask API**: Interact with the blockchain through a RESTful API built with Flask.

## Installation

### Prerequisites
- Python 3.10 or higher
- pip (Python package manager)

### Step 1: Clone the Repository
```bash
git clone https://github.com/yourusername/petroviccoin.git
cd petroviccoin
```

### Step 2: Install Dependencies
```bash
pip install Flask
```

### Step 3: Run the Flask Server
```bash
python3 simple_blockchain.py
```

## Usage

### Running the Server
1. Run the Flask server by executing:
   ```bash
   python3 simple_blockchain.py
   ```
2. The server will start on `http://localhost:5000/`.

### Interacting with the Blockchain
You can interact with the blockchain via the available endpoints using tools like `curl`, Postman, or directly in your browser.

#### 1. View the Blockchain
- URL: `GET /chain`
- Command:
  ```bash
  curl http://localhost:5000/chain
  ```

#### 2. Mine a New Block
- URL: `GET /mine`
- Command:
  ```bash
  curl http://localhost:5000/mine
  ```

#### 3. Create a New Transaction
- URL: `POST /transactions/new`
- Command (for PowerShell):
  ```powershell
  $headers = @{
      "Content-Type" = "application/json"
  }

  $body = @{
      sender = "address1"
      recipient = "address2"
      amount = 5
  }

  $bodyJson = $body | ConvertTo-Json

  Invoke-WebRequest -Uri "http://localhost:5000/transactions/new" -Method POST -Headers $headers -Body $bodyJson
  ```

## Endpoints

- **`GET /`**: Welcome message and list of available endpoints.
- **`GET /chain`**: View the entire blockchain.
- **`GET /mine`**: Mine a new block.
- **`POST /transactions/new`**: Create a new transaction.

## Troubleshooting

### Common Issues

#### 1. Unable to connect to the server
- Ensure the Flask server is running and that the correct IP address or hostname is being used.
- If on the same machine, use `http://localhost:5000/` instead of an IP address.

#### 2. JSON Formatting Errors
- Ensure JSON data is correctly formatted and escaped, especially in PowerShell.

#### 3. 404 Error on Root URL
- Make sure you've added a route for `/` to handle root URL requests.

## Acknowledgments
This project is inspired by the memory of Dražen Petrović, a basketball legend known for his creativity and passion on the court. It aims to encapsulate his spirit in the form of a simple, educational blockchain application.
```
