---
title: Create Your Own Pair
weight: 30
---

PLEASE CHECK [HERE](#important) for additional action on XPLA Chain

## Instantiation by Contract Address

You should use the **Dezswap** token factory contract.

- cube testnet: `xpla1...`
- hypercube testnet: `xpla1`

The JSON message format is as follows:

```json
{
  "create_pair": {
    "asset_infos": [
      {
        "token": {
          "contract_addr": "xpla1..."
        }
      },
      {
        "native_token": {
          "denom": "afet"
        }
      }
    ]
  }
}
```

This is a JSON constructor of pair contract.

- A token pair can be either, contract-based token, or XPLA Chain native / IBC token
  - `asset_infos[x].token.contract_addr`: Contract-basd token *address* is entered here.
  - `asset_infos[x].native_token.denom`: XPLA Chain native / IBC token *denominator* is entered here.

Then, you may execute the contract with the organized JSON above.

## Token Register For Dezswap

- If you want to register a brand-new XPLA Chain native or IBC token that are not listed yet, please find Dezswap team on [#Dezswap discord](https://discord.gg/ZQ2ps5H64t) (for metadata)
