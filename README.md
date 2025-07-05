# Provably Random Raffle Contracts

## About

This project implements a provably random smart contract lottery using Solidity, Chainlink VRF v2.5, and Chainlink Automation. It is designed for educational and demonstration purposes.

## Features

1. Users can enter the raffle by paying a ticket fee. All ticket fees are pooled as the prize for the winner.
2. The lottery automatically draws a winner at regular intervals.
3. Chainlink VRF is used to generate a provably random number for winner selection.
4. Chainlink Automation triggers the lottery draw on schedule.
5. Includes scripts for deploying, funding, and managing Chainlink VRF subscriptions.
6. Comprehensive unit tests using Foundry.

## Getting Started

### Prerequisites

- [Foundry](https://book.getfoundry.sh/)
- Node.js & npm (for Chainlink contracts and scripts)
- An Ethereum node or local Anvil instance

### Installation

```bash
git clone <this-repo>
cd foundry-smart-contract-lottery-f23
forge install
```

### Usage

#### Deploy Contracts

```bash
forge script script/DeployRaffle.s.sol --broadcast --rpc-url <YOUR_RPC_URL>
```

#### Create and Fund VRF Subscription (for local testing)

```bash
forge script script/Interactions.s.sol:CreateSubscription --broadcast --rpc-url <YOUR_RPC_URL>
forge script script/Interactions.s.sol:FundSubscription --broadcast --rpc-url <YOUR_RPC_URL>
forge script script/Interactions.s.sol:AddConsumer --broadcast --rpc-url <YOUR_RPC_URL>
```

#### Run Tests

```bash
forge test
```

### Directory Structure

- `src/` - Main contract code
- `test/` - Unit tests
- `script/` - Deployment and interaction scripts
- `lib/` - External dependencies

## Configuration

Edit `script/HelperConfig.s.sol` to set network-specific parameters such as VRF coordinator, subscription ID, and LINK token address.

## License

MIT

## Acknowledgements

- [Chainlink VRF](https://docs.chain.link/vrf/v2-5/introduction/)
- [Foundry](https://book.getfoundry.sh/)
