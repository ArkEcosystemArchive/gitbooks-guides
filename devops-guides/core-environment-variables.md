---
description: >-
  To operate a node in any ARK network, you need to provide configuration to it
  one way or another.
---

# Core Environment Variables

ARK Core allows you to use a [.env](https://github.com/bevry/envfile) file to provide a configuration that is environment specific without having to touch the `~/.config/ark-core/{network}/plugins.js` file. The `.env` file needs to be stored at `~/.config/ark-core/{network}/.env`.

| Variable                              | Plugin                               | Default      |
|---------------------------------------|--------------------------------------|--------------|
| CORE_EXCHANGE_JSON_RPC_ENABLED        | @arkecosystem/core-exchange-json-rpc | false        |
| CORE_EXCHANGE_JSON_RPC_HOST           | @arkecosystem/core-exchange-json-rpc | "0.0.0.0"    |
| CORE_EXCHANGE_JSON_RPC_PORT           | @arkecosystem/core-exchange-json-rpc | 8080         |
| CORE_EXPLORER_HOST                    | @arkecosystem/core-explorer          | "0.0.0.0"    |
| CORE_EXPLORER_PORT                    | @arkecosystem/core-explorer          | 4200         |
| CORE_LOG_LEVEL                        | @arkecosystem/core-logger-pino       | "debug"      |
| CORE_LOG_LEVEL_FILE                   | @arkecosystem/core-logger-pino       | "trace       |
| CORE_API_DISABLED                     | @arkecosystem/core-api               | false        |
| CORE_API_HOST                         | @arkecosystem/core-api               | "0.0.0.0"    |
| CORE_API_PORT                         | @arkecosystem/core-api               | 4003         |
| CORE_API_CACHE_TIMEOUT                | @arkecosystem/core-api               | 8000         |
| CORE_API_SSL                          | @arkecosystem/core-api               | false        |
| CORE_API_SSL_HOST                     | @arkecosystem/core-api               | "0.0.0.0"    |
| CORE_API_SSL_PORT                     | @arkecosystem/core-api               | 8443         |
| CORE_API_RATE_LIMIT                   | @arkecosystem/core-api               | true         |
| CORE_API_RATE_LIMIT_USER_LIMIT        | @arkecosystem/core-api               | 300          |
| CORE_API_RATE_LIMIT_USER_EXPIRES      | @arkecosystem/core-api               | 60000        |
| CORE_WEBHOOKS_ENABLED                 | @arkecosystem/core-webhooks          | false        |
| CORE_WEBHOOKS_HOST                    | @arkecosystem/core-webhooks          | "0.0.0.0"    |
| CORE_WEBHOOKS_PORT                    | @arkecosystem/core-webhooks          | 4004         |
| CORE_WEBHOOKS_TIMEOUT                 | @arkecosystem/core-webhooks          | 1500         |
| CORE_P2P_HOST                         | @arkecosystem/core-p2p               | "0.0.0.0"    |
| CORE_P2P_PORT                         | @arkecosystem/core-p2p               | 4002         |
| CORE_P2P_MAX_PEERS_SAME_SUBNET        | @arkecosystem/core-p2p               | 5            |
| CORE_P2P_RATE_LIMIT                   | @arkecosystem/core-p2p               | 100          |
| CORE_TRANSACTION_POOL_DISABLED        | @arkecosystem/core-transaction-pool  | false        |
| CORE_MAX_TRANSACTIONS_IN_POOL         | @arkecosystem/core-transaction-pool  | 100000       |
| CORE_TRANSACTION_POOL_MAX_PER_SENDER  | @arkecosystem/core-transaction-pool  | 300          |
| CORE_TRANSACTION_POOL_MAX_PER_REQUEST | @arkecosystem/core-transaction-pool  | 40           |
| CORE_VOTE_REPORT_HOST                 | @arkecosystem/core-vote-report       | "0.0.0.0"    |
| CORE_VOTE_REPORT_PORT                 | @arkecosystem/core-vote-report       | 4006         |
| CORE_VOTE_REPORT_DELEGATE_ROWS        | @arkecosystem/core-vote-report       | 80           |
| CORE_WALLET_API_HOST                  | @arkecosystem/core-wallet-api        | "0.0.0.0"    |
| CORE_WALLET_API_PORT                  | @arkecosystem/core-wallet-api        | 4040         |
| CORE_DB_HOST                          | @arkecosystem/core-database-postgres | "localhost"  |
| CORE_DB_PORT                          | @arkecosystem/core-database-postgres | 5432         |
| CORE_DB_DATABASE                      | @arkecosystem/core-database-postgres | "ark_devnet" |
| CORE_DB_USERNAME                      | @arkecosystem/core-database-postgres | "ark"        |
| CORE_DB_PASSWORD                      | @arkecosystem/core-database-postgres | "password"   |
| CORE_API_NO_ESTIMATED_TOTAL_COUNT     | @arkecosystem/core-database-postgres | false        |
| CORE_P2P_PORT                         | @arkecosystem/core-forger            | 4000         |



