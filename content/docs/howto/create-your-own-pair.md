---
title: Create Your Own Pair
weight: 30
---

{{< tip "warning" >}}
**Important**

Please check [Token Register for Dezswap]({{< relref "#token-register-for-dezswap" >}}) for additional action on XPLA Chain
{{< /tip >}}


## Instantiation by Contract Address

You should use the **Dezswap** [token factory contract]({{< relref "/docs/resources/contract-addresses" >}}).

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
          "denom": "axpla"
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

>If you want to register a brand-new XPLA Chain native or IBC token that are not listed yet, please find Dezswap team on [#Dezswap discord](https://discord.gg/ZQ2ps5H64t) (for metadata)

## Provide initial liquidity

**Dezswap** pair contract knows the swap rate by the both of the remained assets on the pool. But if you have just created your own pair but no liquidity provided, The contract cannot calculate the rate and all swap & swap simulation raise fail. So, **Dezswap** UI does not list the pair unless the initial liquidity is provided. So, if you want finalize the listing, you should provide the initial liquidity and it should be done on CLI.

#### Increase allowance (CW20 token)

If one of or both of assets of the pair are CW20, you should execute `increase_allowance` before providing liquidity. You may follow the instruction from [here](/docs/reference/token/#increasedecrease-allowance). Don't have to do this action of native tokens like `XPLA`.

- Make sure that you should input the pair contract address on `spender`.
- Make sure the input number `amount` that the number is multiplied by the decimal.

e.g:

```bash
xplad tx wasm execute <token_address> '{"increase_allowance":{"spender":"<pair_address>","amount":"<amount_with_decimal>","expires":{"never":{}}}}' --fees 200000000000000atestfet --from <your_key_name_on_local>
```

#### Provide liquidity

Now you can provide the initial liquidity. Replace to your parameter and execute it!\
Make sure that:

- The native token part should be input on both of contract & bash args, and the amount should be same.
- In `--amount` args, no space between the amount and the denom like `<same_amount_above>atestfet`.

```bash
xplad tx wasm execute <pair_address> '{"provide_liquidity":{"assets":[{"info":{"token":{"contract_addr":"<token_address>"}},"amount":"<amount_with_decimal>"},{"info":{"native_token":{"denom":"atestfet"}},"amount":"<amount_with_decimal>"}]}}' --gas 600000 --fees 600000000000000atestfet --from <your_key_name_on_local> --amount <same_amount_above>atestfet
```

