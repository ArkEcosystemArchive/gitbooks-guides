---
description: >-
  To operate a node in any ARK network, you need to provide configuration to it
  one way or another.
---

# Core Environment Variables

ARK Core allows you to use a [.env](https://github.com/bevry/envfile) file to provide a configuration that is environment specific without having to touch the `~/.config/ark-core/{network}/plugins.js` file. The `.env` file needs to be stored at `~/.config/ark-core/{network}/.env`.

| Variable | Plugin | Default |
| :--- | :--- | :--- |
| CORE\_DB\_HOST | @arkecosystem/core-database-postgres | localhost |
| CORE\_DB\_PORT | @arkecosystem/core-database-postgres | 5432 |
| CORE\_DB\_USERNAME | @arkecosystem/core-database-postgres | ark |
| CORE\_DB\_PASSWORD | @arkecosystem/core-database-postgres | password |
| CORE\_DB\_DATABASE | @arkecosystem/core-database-postgres | ark\_devnet |
| CORE\_P2P\_HOST | @arkecosystem/core-p2p | 0.0.0.0 |
| CORE\_P2P\_PORT | @arkecosystem/core-p2p | 4002 |
| CORE\_API\_HOST | @arkecosystem/core-api | 0.0.0.0 |
| CORE\_API\_PORT | @arkecosystem/core-api | 4003 |
| CORE\_WEBHOOKS\_HOST | @arkecosystem/core-webhooks | 0.0.0.0 |
| CORE\_WEBHOOKS\_PORT | @arkecosystem/core-webhooks | 4004 |
| CORE\_JSON\_RPC\_HOST | @arkecosystem/core-json-rpc | 0.0.0.0 |
| CORE\_JSON\_RPC\_PORT | @arkecosystem/core-json-rpc | 8080 |

