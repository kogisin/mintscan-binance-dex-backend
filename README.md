<p align="center">
  <a href="https://www.cosmostation.io" target="_blank" rel="noopener noreferrer"><img width="100" src="https://user-images.githubusercontent.com/20435620/55696624-d7df2e00-59f8-11e9-9126-edf9a40b11a8.png" alt="Cosmostation logo"></a>
</p>

<h2 align="center">
    Mintscan Explorer's Backend for Binance Chain 
</h2>

*:star: Developed / Developing by [Cosmostation](https://www.cosmostation.io/)*

## Overview

This project is sponsored by [Binance X Fellowship Program](https://binancex.dev/fellowship.html). The program supports talented developers and researchers in creating free and open-source software that would enable new innovations and businesses in the crypto community.

This repository provides backend code for [Mintscan Block Explorer for Binance Chain](https://binance.mintscan.io/), and you can find frontend code in [this repository](https://github.com/cosmostation/mintscan-binance-dex-frontend).

**_Note that this repository is currently being developed meaning that most likely there will be many breaking changes._**

## Prerequisite

- Requires [Go 1.14+](https://golang.org/dl/)

- Prepare endpoints for [Binance Chain Node RPC](https://docs.binance.org/api-reference/node-rpc.html) and [API Server](https://docs.binance.org/api-reference/api-server.html)

- Prepare PostgreSQL Database

## Folder Structure

    /
    |- chain-exporter
    |- mintscan
    |- stats-exporter

#### Chain Exporter

[chain-exporter](https://github.com/cosmostation/mintscan-binance-dex-backend/chain-exporter) watches a full node of Binance Chain and export chain data into PostgreSQL database.

#### Mintscan

[mintscan](https://github.com/cosmostation/mintscan-binance-dex-backend/mintscan) provides any necesarry custom APIs.

#### Stats Exporter

[stats-exporter](https://github.com/cosmostation/mintscan-binance-dex-backend/stats-exporter) creates cron jobs to export market data to build chart history API.

## Configuration

For configuration, it uses human readable data-serialization configuration file format called [YAML](https://en.wikipedia.org/wiki/YAML).

To configure `chain-exporter` | `mintscan` | `stats-exporter`, you need to configure  `config.yaml` file in each folder. Reference `example.yaml`.

**_Note that the configuration needs to be passed in via `config.yaml` file, so make sure to change the name to `config.yaml`._**

## Install

#### Git clone this repo
```shell
git clone https://github.com/cosmostation/mintscan-binance-dex-backend.git
```

#### Build by Makefile
```shell
cd mintscan-binance-dex-backend/chain-exporter
make build

cd mintscan-binance-dex-backend/mintscan
make build

cd mintscan-binance-dex-backend/stats-exporter
make build
```

## Database 

This project uses [Golang ORM with focus on PostgreSQL features and performance](https://github.com/go-pg/pg). Once `chain-exporter` begins to run, it creates the following database tables if not exist already.

- Block
- PreCommit
- Transaction
- Validator

## Contributing

We encourage and support an active, healthy community of contributors — any contribution, improvements, and suggestions are always welcome! Details are in the [contribution guide](https://github.com/cosmostation/mintscan-binance-dex-backend/docs/CONTRIBUTING.md)

## Our Services and Community 

- [Official Website](https://www.cosmostation.io)
- [Mintscan Explorer](https://www.mintscan.io)
- [Web Wallet](https://wallet.cosmostation.io)
- [Android Wallet](https://bit.ly/2BWex9D)
- [iOS Wallet](https://apple.co/2IAM3Xm)
- [Telegram - International](https://t.me/cosmostation)

## License

Released under the [Apache 2.0 License](https://github.com/cosmostation/mintscan-binance-dex-backend/LICENSE).