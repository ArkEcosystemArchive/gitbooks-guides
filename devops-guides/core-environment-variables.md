---
description: >-
  To operate a node in any ARK network, you need to provide configuration to it
  one way or another.
---

# Core Environment Variables

ARK Core allows you to use a [.env](https://github.com/bevry/envfile) file to provide a configuration that is environment specific without having to touch the `~/.config/ark-core/{network}/plugins.js` file. The `.env` file needs to be stored at `~/.config/ark-core/{network}/.env`.

| Variable | Plugin | Default |
| :--- | :--- | :--- |
| CORE\_EXCHANGE\_JSON\_RPC\_ENABLED | @arkecosystem/core-exchange-json-rpc | false |
| CORE\_EXCHANGE\_JSON\_RPC\_HOST | @arkecosystem/core-exchange-json-rpc | "0.0.0.0" |
| CORE\_EXCHANGE\_JSON\_RPC\_PORT | @arkecosystem/core-exchange-json-rpc | 8080 |
| CORE\_EXPLORER\_HOST | @arkecosystem/core-explorer | "0.0.0.0" |
| CORE\_EXPLORER\_PORT | @arkecosystem/core-explorer | 4200 |
| CORE\_LOG\_LEVEL | @arkecosystem/core-logger-pino | "debug" |
| CORE\_LOG\_LEVEL\_FILE | @arkecosystem/core-logger-pino | "trace |
| CORE\_API\_DISABLED | @arkecosystem/core-api | false |
| CORE\_API\_HOST | @arkecosystem/core-api | "0.0.0.0" |
| CORE\_API\_PORT | @arkecosystem/core-api | 4003 |
| CORE\_API\_CACHE\_TIMEOUT | @arkecosystem/core-api | 8000 |
| CORE\_API\_SSL | @arkecosystem/core-api | false |
| CORE\_API\_SSL\_HOST | @arkecosystem/core-api | "0.0.0.0" |
| CORE\_API\_SSL\_PORT | @arkecosystem/core-api | 8443 |
| CORE\_API\_RATE\_LIMIT | @arkecosystem/core-api | true |
| CORE\_API\_RATE\_LIMIT\_USER\_LIMIT | @arkecosystem/core-api | 300 |
| CORE\_API\_RATE\_LIMIT\_USER\_EXPIRES | @arkecosystem/core-api | 60000 |
| CORE\_WEBHOOKS\_ENABLED | @arkecosystem/core-webhooks | false |
| CORE\_WEBHOOKS\_HOST | @arkecosystem/core-webhooks | "0.0.0.0" |
| CORE\_WEBHOOKS\_PORT | @arkecosystem/core-webhooks | 4004 |
| CORE\_WEBHOOKS\_TIMEOUT | @arkecosystem/core-webhooks | 1500 |
| CORE\_P2P\_HOST | @arkecosystem/core-p2p | "0.0.0.0" |
| CORE\_P2P\_PORT | @arkecosystem/core-p2p | 4002 |
| CORE\_P2P\_MAX\_PEERS\_SAME\_SUBNET | @arkecosystem/core-p2p | 5 |
| CORE\_P2P\_RATE\_LIMIT | @arkecosystem/core-p2p | 100 |
| CORE\_TRANSACTION\_POOL\_DISABLED | @arkecosystem/core-transaction-pool | false |
| CORE\_MAX\_TRANSACTIONS\_IN\_POOL | @arkecosystem/core-transaction-pool | 100000 |
| CORE\_TRANSACTION\_POOL\_MAX\_PER\_SENDER | @arkecosystem/core-transaction-pool | 300 |
| CORE\_TRANSACTION\_POOL\_MAX\_PER\_REQUEST | @arkecosystem/core-transaction-pool | 40 |
| CORE\_VOTE\_REPORT\_HOST | @arkecosystem/core-vote-report | "0.0.0.0" |
| CORE\_VOTE\_REPORT\_PORT | @arkecosystem/core-vote-report | 4006 |
| CORE\_VOTE\_REPORT\_DELEGATE\_ROWS | @arkecosystem/core-vote-report | 80 |
| CORE\_WALLET\_API\_HOST | @arkecosystem/core-wallet-api | "0.0.0.0" |
| CORE\_WALLET\_API\_PORT | @arkecosystem/core-wallet-api | 4040 |
| CORE\_DB\_HOST | @arkecosystem/core-database-postgres | "localhost" |
| CORE\_DB\_PORT | @arkecosystem/core-database-postgres | 5432 |
| CORE\_DB\_DATABASE | @arkecosystem/core-database-postgres | "ark\_devnet" |
| CORE\_DB\_USERNAME | @arkecosystem/core-database-postgres | "ark" |
| CORE\_DB\_PASSWORD | @arkecosystem/core-database-postgres | "password" |
| CORE\_API\_NO\_ESTIMATED\_TOTAL\_COUNT | @arkecosystem/core-database-postgres | false |
| CORE\_P2P\_PORT | @arkecosystem/core-forger | 4000 |

