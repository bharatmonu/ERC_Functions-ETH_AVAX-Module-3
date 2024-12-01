# ERC Smart Contract Functions 

This is a token mint burn and transfer system. The contract allows an administrator to mint new tokens, users to transfer tokens, and burn tokens from their balances. It is written in Solidity and deployed on the remix ide vm.

---

## Features

1. **Minting Tokens**  
   The contract owner (admin) can mint tokens and add them to their balance.  
   - Increases the total supply of tokens.
   - Can only be performed by the admin.

2. **Burning Tokens**  
   Users can burn tokens from their own balance.  
   - Decreases the total supply of tokens.
   - Requires a sufficient balance.

3. **Transferring Tokens**  
   Users can transfer tokens to another address.  
   - Ensures that the sender has a sufficient balance before allowing the transfer.

---

## Smart Contract Details

- **Token Name:** `japan`
- **Token Abbreviation:** `jp`
- **Total Supply:** Starts at `0`.

### State Variables

| Variable       | Type      | Description                                  |
|----------------|-----------|----------------------------------------------|
| `admin`        | `address` | Stores the address of the contract owner.    |
| `tokenName`    | `string`  | Name of the token (fixed: "japan").          |
| `tokenAbbrv`   | `string`  | Abbreviation of the token (fixed: "jp").     |
| `totalTokens`  | `uint256` | Total number of tokens in circulation.       |
| `balances`     | `mapping` | Keeps track of token balances by address.    |

---

## Functions

### 1. **Constructor**
```solidity
constructor()
```
- Sets the `admin` as the contract deployer.
- Initializes the `admin` balance with `totalTokens`.

### 2. **Mint Tokens**
```solidity
function mintTokens(address _address, uint256 _amount) public
```
- Increases the total token supply.
- Adds `_amount` to `_address`'s balance.
- **Only callable by the admin.**

### 3. **Burn Tokens**
```solidity
function burnTokens(uint256 _amount) public
```
- Reduces the caller's token balance by `_amount`.
- Decreases the total token supply.
- Fails if the caller's balance is insufficient.

### 4. **Transfer Tokens**
```solidity
function transferTokens(address _toAddress, uint256 _amount) public
```
- Transfers `_amount` from the caller to `_toAddress`.
- Ensures the caller has a sufficient balance.

---

## Usage

### Deploying the Contract
1. Open an Ethereum development environment like [Remix](https://remix.ethereum.org/).
2. Copy the smart contract code into a new file.
3. Compile the contract using the Solidity compiler (`^0.8.18`).
4. Deploy the contract using a wallet address as the admin.

### Interacting with the Contract
1. **Minting Tokens:**  
   - Call `mintTokens` with the admin address and the amount to mint.
2. **Burning Tokens:**  
   - Call `burnTokens` with the amount to burn.
3. **Transferring Tokens:**  
   - Call `transferTokens` with the recipient address and the amount to transfer.

---

## Requirements

- **Solidity :** `^0.8.18`
- [Remix IDE](https://remix.ethereum.org/)  

---

## Author 

- Bharat Kumar

## License

This project is licensed under the MIT License. See the LICENSE file for details.
