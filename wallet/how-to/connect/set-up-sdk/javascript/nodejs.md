---
sidebar_label: Node.js
sidebar_position: 5
---

# Use MetaMask SDK with Node.js

You can import [MetaMask SDK](../../../../concepts/sdk/index.md) into your Node.js dapp to enable your users
to easily connect to the MetaMask browser extension and MetaMask Mobile.
The SDK for Node.js has the [same prerequisites](index.md#prerequisites) as for standard JavaScript.

:::tip example
See the [Node.js SDK example](https://github.com/MetaMask/metamask-sdk/tree/main/packages/examples/nodejs)
for advanced use cases.
:::

## Steps

### 1. Install the SDK

In your project directory, install the SDK using Yarn or npm:

```bash
yarn add @metamask/sdk
```

or

```bash
npm i @metamask/sdk
```

### 2. Import the SDK

In your project script, add the following to import the SDK:

```javascript
import { MetaMaskSDK } from '@metamask/sdk';
```

### 3. Instantiate the SDK

Instantiate the SDK using any [options](../../../../reference/sdk-js-options.md):

```javascript
const MMSDK = new MetaMaskSDK(options);

const ethereum = MMSDK.getProvider(); // You can also access via window.ethereum
```

### 4. Use the SDK

Use the SDK by calling any [provider API methods](../../../../reference/provider-api.md).
Always call [`eth_requestAccounts`](../../../../reference/rpc-api.md#eth_requestaccounts) using
[`ethereum.request()`](../../../../reference/provider-api.md#ethereumrequestargs) first, since it
prompts the installation or connection popup to appear.

```javascript
ethereum.request({ method: 'eth_requestAccounts', params: [] });
```
