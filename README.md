# Aleo Learn & Earn Workshop: Auction Bidding

## Overview
This project is an **auction bidding program** built using **Aleo's Zero-Knowledge (ZK) technology**. It allows users to place bids on an item, ensuring that all bids meet a minimum threshold. The auctioneer then resolves the auction by selecting the highest bid and transferring ownership to the winner.

## Deployment Details
- **Deployment ID:** `at1x3wjncfe6qt8mmgp49qxa5v5xdwj6xsaxmtndcf8nz4g9fz9vqrql838wf`
- **Deployment URL:** [View on Aleo Testnet](https://testnet.aleoscan.io/transaction?id=at1asph5gzfcv8e97825rpxvlrv4trn40s0stcm90sckuszm4nsmgpqrjs0av)

## Execution
- **Transaction ID:** `at1asph5gzfcv8e97825rpxvlrv4trn40s0stcm90sckuszm4nsmgpqrjs0av`


## Features
1. **Bid Placement:** Users can place a bid by calling `place_bid(bidder, amount)`. The amount must be greater than **5000**.
2. **Bid Storage:** The bid is recorded as a `Bid` record with the **auctioneer as the owner**.
3. **Auction Resolution:** The auctioneer calls `resolve(first, second)` to determine the winner:
   - The highest bid wins.
   - In case of a tie, the first bid placed is chosen.
4. **Finalization & Transfer:** The auctioneer calls `finish(bid)`, marking the winning bid and transferring ownership of the bid record to the winner.

## How It Works
1. **Users Place Bids**
   ```sh
   aleo run place_bid aleo1bidderaddress 6000
   ```
   - Ensures the bid amount is greater than **5000**.
   - The bid is stored under the auctioneer’s ownership.

2. **Auctioneer Resolves the Auction**
   ```sh
   aleo run resolve aleo1bid1 aleo1bid2
   ```
   - Selects the highest bid.
   - If tied, chooses the first bid.

3. **Finalization & Transfer of Ownership**
   ```sh
   aleo run finish aleo1winningbid
   ```
   - Transfers bid ownership to the winner.


