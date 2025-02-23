# Reactive Rewards Smart Contract (Origin-Destination System)
The Reactive Rewards Smart Contract is a decentralized and automated reward distribution system that seamlessly integrates with the Reactive Network. Designed to manage donations, goal-based rewards, and real-time event-triggered transactions, this contract ensures efficient and trustless execution using the Reactive Library (reactive-lib).

# How It Works
Origin Contract (BasicRewardsEthL1.sol)

Accepts donations from users via a Donate button in the dApp.

Allows the contract owner to set goal completion rewards when a user completes a fitness task (e.g., 10 push-ups).

Users claim rewards after completing a goal.


Reactive Contract (RewardsReactive)

Listens for SetReward events on the origin contract.

Automatically triggers the claim() function when a reward is set.

Uses the Reactive Network to enable event-driven automation on-chain.

# Key Features
Event-Driven Automation – Eliminates manual transactions with auto-triggered claims.
Seamless Donations & Rewards – Supports donations and transparent reward tracking.
Efficient & Gas-Optimized – Uses the Reactive Network for minimal gas overhead.
Trustless Execution – Ensures fair and verifiable reward distribution.

This smart contract is ideal for fitness dApps, decentralized incentives, and Web3-based reward programs, providing a fully autonomous and reactive blockchain experience.

# Smart Contract Flow
* sequenceDiagram <br>
    participant Backend <br>
    participant RewardsEth <br>
    participant ReactiveNetwork <br>
    participant RewardsReactive <br>
    Backend ->> RewardsEth: Send goal completion request <br>
    RewardsEth ->> RewardsEth: Set reward for user <br>
    RewardsEth ->> ReactiveNetwork: Emit `SetReward` Event <br>
    ReactiveNetwork ->> RewardsReactive: Detects `SetReward` <br>
    RewardsReactive ->> RewardsEth: Calls `claim()` <br>
    RewardsEth ->> User: Transfers reward ETH 
