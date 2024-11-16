Step 3: Running the Blockchain Code
The goal is to run the implemented blockchain and demonstrate its functionality in a typical PC environment. Below is a detailed explanation of the blockchain system, its components, and instructions for setting it up and testing it. Screenshots are referenced where relevant.
Description of the Code
1. Blockchain Server
The blockchain server is the core of the system, responsible for maintaining the blockchain, validating transactions, and ensuring network synchronization.
Purpose:
Serves as the backend where all computational logic resides.
Handles block creation, Proof of Work (PoW) mining, transaction validation, and conflict resolution.
Key Components: 
Blockchain Class:
Maintains:
	•  The actual chain of blocks (chain).
	• Pending transactions (transactions) awaiting validation.
	•  A set of connected nodes (nodes) for peer-to-peer communication.
Provides methods to:
	•	Add new transactions to the pending pool.
	•	Mine blocks using the PoW algorithm.
	•	Synchronize the chain by resolving conflicts between nodes.
Mining Functionality:
	•	The server mines new blocks by solving a cryptographic puzzle using the hash of the previous block.
	•	This ensures immutability and integrity of the blockchain.
REST APIs:
	•	/mine: Mines a new block and adds it to the chain.
	•	/chain: Returns the full blockchain data for verification.
	•	/transactions/new: Accepts and validates new transactions.

2. Blockchain Client
The client provides a user-friendly interface for interacting with the blockchain. Users can generate wallets, create transactions, and view the blockchain.
Purpose:
Acts as the front-end interface for blockchain users, enabling secure and easy interaction.
Key Features:
Wallet Generator:
	•	Uses RSA encryption to generate a pair of keys (public and private).
	•	The public key acts as the user’s address, while the private key is used for signing transactions.
Transaction Creation:
	•	Allows users to initiate cryptocurrency transactions by specifying:
	•	Sender’s and recipient’s public keys.
	•	The transaction amount.
	•	The system generates a unique digital signature to ensure authenticity.
Transaction Viewing:
	•	Displays pending and confirmed transactions in the blockchain.
	•	Provides transparency to users.
3. Technologies Used
The implementation relies on the following technologies:
	•	Python: Core programming language for blockchain logic.
	•	PyCryptodome: Library for cryptographic operations such as RSA encryption and SHA-256 hashing.
	•	Flask: Provides the framework for building REST APIs that connect the server and client.

Instructions to Run the Blockchain
a. System Requirements
The code is platform-independent and runs on both Windows and Mac. Ensure the following:
	•	Python: Version 3.6 or higher installed.
	•	Libraries:
	•	Flask: Provides REST API functionality.
	•	PyCryptodome: Handles encryption and hashing operations.

b. Installation and Setup
  Install Python Libraries:
	•	Open a terminal or command prompt and execute the following command to install the required libraries:
pip install flask pycryptodome

Prepare the Code:
	•	Ensure the project folder includes:
	•	blockchain_server.py (server-side code).
	•	blockchain_client.py (client-side code).
	•	Associated HTML templates for the dashboard interface.
Running the Blockchain
Start the Blockchain Server:
	•	Navigate to the project directory in the terminal and run:

python blockchain_server.py
•	This initializes the server, enabling it to process transactions and mine blocks.
Start the Blockchain Client:
	•	In a separate terminal window, execute:
python blockchain_client.py
•	This launches the client interface.
Access the Dashboard:
	•	Open a web browser and navigate to http://127.0.0.1:5000 to interact with the blockchain.
Using the Blockchain
1. Generating Wallets

	•	Navigate to the Wallet Generator tab on the dashboard.
	•	Click the button to generate a Public/Private Key Pair.
	•	Use the public key as the user’s address for sending or receiving transactions.

2. Creating a Transaction

	•	Go to the Make Transaction tab.
	•	Input the following:
	•	Sender’s public key.
	•	Recipient’s public key.
	•	Transaction amount.
	•	Confirm the transaction to generate a unique digital signature.

3. Mining Blocks

	•	Switch to the Mine tab.
	•	Click the “Mine” button to process the pending transactions.
	•	The system performs Proof of Work (PoW), validates the transactions, and adds a new block to the blockchain.
4. Viewing the Blockchain

	•	Access the View Blockchain tab.
	•	Inspect:
	•	The chain of blocks, including their transaction details.
	•	Hash values for verifying block integrity.
Reliability and Testing

	•	Transaction Validation:
	•	Ensures all transactions are signed and verified.
	•	Mining Verification:
	•	Validates blocks via PoW and links them securely.
	•	Multi-Node Consistency:
	•	Simulates node synchronization to resolve conflicts and ensure the chain is consistent.

By following the steps and using the screenshots, the blockchain can be demonstrated to run reliably in a standard PC environment.

