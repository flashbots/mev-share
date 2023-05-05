# `eth_sendBundle`

Matchmakers can use the `eth_sendBundle` method to send a bundle of transactions to a block builder. Specifically, the `refund-recipient` version of `eth_sendBundle` extends the [standard `eth_sendBundle` API](https://docs.flashbots.net/flashbots-auction/searchers/advanced/rpc-endpoint#eth_sendbundle) to support two additional fields (`refundPercent` and `refundRecipient`) which can optionally be set to specify how refunds from MEV-Share should be distributed.

## JSON-RPC Scheme

```typescript
{
  jsonrpc: "2.0",
  id: 1,
  method: "eth_sendBundle",
  params: [{
      txs: Array<string>,
      blockNumber: string,
      minTimestamp?: number,
      maxTimestamp?: number,
      revertingTxHashes?: Array<string>,
      replacementUuid?: string,
      refundPercent?: number,
      refundRecipient?: string,
  }]
}
```

_NOTE: Optional fields are marked with a `?`._

## `txs`

A list of signed transactions to execute in an atomic bundle.

## `blockNumber`

A hex encoded block number for which this bundle is valid on.

## `minTimestamp`

The minimum timestamp for which this bundle is valid, in seconds since the unix epoch.

## `maxTimestam`

The maximum timestamp for which this bundle is valid, in seconds since the unix epoch.

## `revertingTxHashes`

A list of tx hashes that are allowed to revert or be discarded from the beginning of the bundle.

## `replacementUuid`

UUID that can be used to cancel/replace this bundle.

## `refundPercent`

The percent(from 0 to 99) of full bundle ETH reward that should be passed back to the user(`refundRecipient`) at the end of the bundle.

## `refundRecipient`

Address of the wallet that will receive the ETH reward refund from this bundle, default value = EOA of the first transaction inside the bundle.

If the `refundPercent` field is set, the builder will keep exactly 100% - `refundPercent` of the bundle's total ETH reward and pass the rest to the user.

## Example

Request:

```typescript
{
  jsonrpc: "2.0",
  id: 1,
  method: "eth_sendBundle",
  params: [
    {
      "txs": ["0x123abc...", "0x456def..."],
      "blockNumber": "0xb63dcd",
      "minTimestamp": 0,
      "maxTimestamp": 1615920932
    }
  ]
}
```

Response:

```typescript
{
  jsonrpc: "2.0",
  id: "123",
  result: {
    "bundleHash": "0x2228f5d8954ce31dc1601a8ba264dbd401bf1428388ce88238932815c5d6f23f"
  }
}
```