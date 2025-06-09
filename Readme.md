**Note**: This example is adapted from the official [rust-libp2p file-sharing example](https://github.com/libp2p/rust-libp2p/tree/master/examples/file-sharing).

# Simple File Sharing with Provider and Retriever Nodes

This project demonstrates a simple peer-to-peer file sharing mechanism using provider and retriever nodes. A provider shares a file on the network, and a retriever can fetch it using a known name and peer address.

## Prerequisites

- Rust and Cargo installed
- Terminal access

## Getting Started

### 1. Start a File Provider

In one terminal window, run the following command:

```bash
cargo run -- --listen-address /ip4/127.0.0.1/tcp/40837 \
          --secret-key-seed 1 \
          provide \
          --path <path-to-your-file> \
          --name <name-for-others-to-find-your-file>
```

### 2. Start a File Retriever

In another terminal window, run the following command:

```bash
cargo run -- --peer /ip4/127.0.0.1/tcp/40837/p2p/12D3KooWPjceQrSwdWXPyLLeABRXmuqt69Rg3sBYbU1Nft9HyQ6X \
          get \
          --name <name-for-others-to-find-your-file>
```
