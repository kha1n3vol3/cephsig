COMING SOON!

![logo](cephsig2.jpg)

### **CEPHSIG(1)** User Commands **CEPHSIG(1)**

#### **NAME**  
`cephsig` - a command-line tool for multisig management

#### **SYNOPSIS**  
`cephsig [OPTIONS] COMMAND [ARGS]...`

#### **DESCRIPTION**  
`cephsig` is a command-line utility for managing multisig wallets and transactions in cryptocurrencies that support multisig functionality. It allows users to create multisig wallets, add or remove signers, set the required number of signatures (threshold), sign transactions, and verify signatures.  

Multisig (multi-signature) technology requires multiple private keys to authorize a transaction, enhancing security by distributing control among multiple parties. This is useful for shared accounts, escrow services, or any scenario where multiple approvals are needed for a transaction.

#### **OPTIONS**  
- `--help`  
  Show this message and exit.  

- `--version`  
  Show the version and exit.

#### **COMMANDS**  
- `create`  
  Create a new multisig wallet.  
  Usage: `cephsig create --signers <signer1> <signer2> ... --threshold <number>`  

- `add-signer`  
  Add a signer to an existing multisig wallet.  
  Usage: `cephsig add-signer --wallet <wallet_id> --signer <new_signer>`  

- `remove-signer`  
  Remove a signer from an existing multisig wallet.  
  Usage: `cephsig remove-signer --wallet <wallet_id> --signer <signer_to_remove>`  

- `set-threshold`  
  Set the required number of signatures for a multisig wallet.  
  Usage: `cephsig set-threshold --wallet <wallet_id> --threshold <new_threshold>`  

- `sign`  
  Sign a transaction with a private key.  
  Usage: `cephsig sign --wallet <wallet_id> --transaction <transaction_data> --private-key <private_key>`  

- `verify`  
  Verify the signatures of a transaction.  
  Usage: `cephsig verify --wallet <wallet_id> --transaction <transaction_data>`

#### **PARAMETERS**  
- `<wallet_id>`  
  The unique identifier of the multisig wallet.  

- `<signer>`  
  The public key or address of a signer.  

- `<threshold>`  
  The number of signatures required to authorize a transaction.  

- `<transaction_data>`  
  The transaction data in a format specific to the cryptocurrency (e.g., hex-encoded for Bitcoin).  

- `<private_key>`  
  The private key used for signing the transaction.

#### **EXAMPLES**  
- Create a new multisig wallet with 3 signers and a threshold of 2:  
  ```
  cephsig create --signers pubkey1 pubkey2 pubkey3 --threshold 2
  ```

- Add a signer to an existing multisig wallet:  
  ```
  cephsig add-signer --wallet wallet123 --signer pubkey4
  ```

- Remove a signer from an existing multisig wallet:  
  ```
  cephsig remove-signer --wallet wallet123 --signer pubkey2
  ```

- Set the threshold for an existing multisig wallet to 3:  
  ```
  cephsig set-threshold --wallet wallet123 --threshold 3
  ```

- Sign a transaction:  
  ```
  cephsig sign --wallet wallet123 --transaction tx_data.hex --private-key privkey1
  ```

- Verify the signatures of a transaction:  
  ```
  cephsig verify --wallet wallet123 --transaction tx_data.hex
  ```
