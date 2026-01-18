# Foundry Fund Me

A crowdfunding smart contract built with Foundry that accepts ETH donations denominated in USD. Uses Chainlink price feeds for ETH/USD conversion with a minimum donation threshold of $5.

## Features

- Accept ETH donations with USD-based minimum threshold
- Chainlink price feed integration for accurate ETH/USD pricing
- Gas-optimized withdrawal function
- Multi-network support (Mainnet, Sepolia, local Anvil)

## Quick Start

```bash
# Clone the repo
git clone https://github.com/manu-cadena/foundry-fund-me
cd foundry-fund-me

# Install dependencies
make install

# Build
make build

# Run tests
make test
```

## Environment Setup

Copy the example environment file and fill in your values:

```bash
cp .env.example .env
```

Required variables:
- `SEPOLIA_RPC_URL` - Your Alchemy/Infura RPC URL for Sepolia
- `ETHERSCAN_API_KEY` - For contract verification
- `ACCOUNT` - Your keystore account name (created with `cast wallet import`)

## Deploy

```bash
# Local (starts Anvil and deploys)
make anvil      # In one terminal
make deploy     # In another terminal

# Sepolia testnet
make deploy-sepolia
```

## Interact with Contract

```bash
# Fund the contract
make fund

# Withdraw funds (owner only)
make withdraw
```

## Other Commands

| Command | Description |
|---------|-------------|
| `make build` | Compile contracts |
| `make test` | Run tests |
| `make snapshot` | Generate gas report |
| `make format` | Format code with forge fmt |
| `make clean` | Clean build artifacts |

## Acknowledgments

Built while learning from the [Cyfrin Updraft](https://updraft.cyfrin.io/) Foundry course.
