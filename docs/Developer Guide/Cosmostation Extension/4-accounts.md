---
sidebar_position: 4
---

# Accounts

Using Cosmostation Extension accounts.

## Get Accounts

### Code using @cosmostation/extension-client

```javascript
const account = await provider.getAccount({ chainName: "cosmos" });
```

### Vanilla Code

```javascript
const accoutn = await window.cosmostation.tendermint.request({
  method: "ten_account",
  params: { chainName: "cosmos" },
});
```

> ### If connected successfully, it will look like below.
>
> ![Provider](/img/developer/extension/2-provider-connected.png)

#### Response

```typescript title="Model"
type AccountResponse = {
  name: string;
  address: string;
  publicKey: Uint8Array;
};
```

```json title="Example"
{
  "name": "account name",
  "address": "cosmos1wgeoiheoighwoighwioeghoweghoiweghiow",
  "publicKey": [
    3, 77, 9, 189, 251, 249, 150, 235, 192, 56, 51, 98, 56, 242, 12, 102, 144,
    211, 89, 42, 187, 170
  ]
}
```

## Request Account (Popup)

### Code using @cosmostation/extension-client

```typescript
const account = await provider.requestAccount({ chainName: "cosmos" });
```

### Vanilla Code

```javascript
const accoutn = await window.cosmostation.tendermint.request({
  method: "ten_requestAccount",
  params: { chainName: "cosmos" },
});
```

#### Response

```typescript title=Model
type RequestAccountResponse = {
  name: string;
  address: string;
  publicKey: Uint8Array;
};
```

```json title=Example
{
  "name": "account name",
  "address": "cosmos1wgeoiheoighwoighwioeghoweghoiweghiow",
  "publicKey": [
    3, 77, 9, 189, 251, 249, 150, 235, 192, 56, 51, 98, 56, 242, 12, 102, 144,
    211, 89, 42, 187, 170
  ]
}
```