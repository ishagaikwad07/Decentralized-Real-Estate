## Overview

This contract enables:
1. Assignment of an agent by the property owner.
2. Purchase of the property by a buyer, with funds directly distributed between the property owner and agent.
3. Transparent ownership verification for the property.

## Requirements

- Solidity Version: ^0.8.0
- Ethereum Wallet: Compatible wallet (e.g., MetaMask) for interaction
- Ether: Buyer needs to transfer 11 Ether for purchasing the property

## Deployment

To deploy this contract:
1. Copy the code 
2. Compile the code using a Solidity compiler (such as in Remix IDE).
3. Deploy to an Ethereum network.

The contract constructor sets the **property owner** as the account deploying the contract.

## Features

- Property Owner Assignment: Only the property owner (the deployer) can assign an agent.
- Agent Restrictions: The agent is restricted from purchasing the property.
- Ownership Transfer: Once the buyer completes the payment, ownership is transferred to the buyer.
- Automated Payments: Agent commission and property owner payment are processed automatically.
- Ownership Check: Any user can check the current ownership status of the property.

## How It Works

1. Contract Creation: The property owner (deployer) initializes the contract.
2. Agent Assignment: The property owner assigns an agent by calling `assignAgent(address)`.
3. House Purchase:
   - A buyer (not the agent) calls `buyHouse()` and transfers exactly 11 Ether.
   - 2 Ether is sent to the agent as commission, and 9 Ether goes to the property owner.
   - Ownership is transferred to the buyer, and `houseSold` is marked `true`.
4. Ownership Verification: The current property owner can be verified by calling `getOwner()`.

## Functions

- assignAgent: Allows the property owner to assign an agent.
- buyHouse: Allows a buyer to purchase the property and transfers funds to the owner and agent.
- getOwner: Returns the address of the current property owner.
