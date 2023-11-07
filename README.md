# ERC20 Token and Vault Smart Contracts

This repository contains two Solidity smart contracts: `ERC20.sol` and `Vault.sol`. The `ERC20` contract represents an ERC-20 token, a widely used standard for fungible tokens on the Ethereum blockchain. The `Vault` contract serves as a mechanism for users to deposit and withdraw tokens while receiving corresponding shares in the vault.

## ERC20.sol

### ERC-20 Token Contract

- **License**: MIT
- **Solidity Version**: 0.8.17

This contract defines a basic implementation of an ERC-20 token, complete with essential functions and events. It includes the following features:

- `totalSupply`: A variable to store the total supply of the token.
- `balanceOf`: A mapping that keeps track of the token balance for each address.
- `allowance`: A double mapping that tracks the allowance granted by one address to another.
- `name`, `symbol`, and `decimals`: Metadata variables that describe the token.
- `Transfer` and `Approval` events: These events are emitted when transfers and approvals occur.

Key functions in this contract include:

- `transfer`: Allows an address to send tokens to another address.
- `approve`: Allows an address to approve another address to spend a certain amount of tokens on their behalf.
- `transferFrom`: Enables an approved address to spend tokens on behalf of another address.
- `mint`: Allows an address to create new tokens, increasing the total supply.
- `burn`: Enables an address to destroy tokens, decreasing the total supply.

This contract serves as a simple example of an ERC-20 token and can be utilized to create and manage tokens on the Ethereum blockchain.

## Vault.sol

### Vault Contract

- **License**: MIT
- **Solidity Version**: 0.8.17

The `Vault` contract is designed to interact with an ERC-20 token, possibly the one defined in `ERC20.sol`. Its primary functionality is to allow users to deposit tokens into the vault, receive corresponding shares in the vault, and later withdraw tokens based on the number of shares they hold. This concept is commonly used in decentralized finance (DeFi) applications and asset management systems.

Key elements of the `Vault` contract include:

- `IERC20`: An interface that defines the functions and events for interacting with an ERC-20 token.
- `token`: An immutable variable that holds the address of an ERC-20 token contract.

Noteworthy functions in this contract are:

- `deposit`: Permits users to deposit tokens into the vault. It calculates the number of "shares" to mint based on the deposited amount and the existing shares in the vault. This allows users to receive shares representing their ownership of the assets in the vault.
- `withdraw`: Allows users to withdraw tokens from the vault, specifying the number of shares they want to burn. The function calculates the amount of tokens to be returned based on the number of shares and the total supply of shares.

The `Vault` contract is useful for managing assets in a more complex way than simple token transfers and can be integrated into larger systems for asset allocation and management.
