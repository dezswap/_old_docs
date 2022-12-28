---
title: Query
weight: 40
---

## How to Send a Query Request

- Command line

```bash
xpladd query wasm contract-state smart <contract_address> '<JSON_formed_message>'
```

ex)

```bash
xpladd query wasm contract-state smart xpla1kmag3937lrl6dtsv29mlfsedzngl9egv5c3apnr468q50gu04zrqea398u '{"pairs":{}}'
```

- RESTFul API

```URL
<light_clinet_address>/cosmwasm/wasm/v1/contract/<contract_address>/smart/<JSON_formed_message_with_base64>
```

ex)

```URL
https://TODO/cosmwasm/wasm/v1/contract/xpla1.../smart/eyJwYWlycyI6e319
```

## How to Organize a Query Message

You may check `<contract>/src/msg.rs` of each contract. <br/>
Here is an example. Query messages are defined as below:

```rust
#[derive(Serialize, Deserialize, Clone, Debug, PartialEq, JsonSchema)]
#[serde(rename_all = "snake_case")]
pub enum QueryMsg {
    Balance { address: <Addr> },
    ...
}
```

This is one of the messages

```rust
Balance { address: <Addr> }
```

You may change it into snake case and add within `{}` as like below:

```json
{"balance": {"address": "<Addr>"}}
```

`Addr` is a type, which is bech32-encoded address `xpla` prefixed.<br />
Here is an example:

```json
{"balance": {"address": "xpla1..."}}
```

This rule also can be applied to other messages, so you can utilize this guide as a reference for your practice.
