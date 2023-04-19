# Event Stream

Events on MEV-Share are distributed via an SSE endpoint. Searchers listen to this endpoint to receive a stream of new events, which contain data they can use in their bundles.

## Event Scheme

```typescript
{
    hash: string,
    logs?: LogParams[],
    txs: Array<{
        to?: string,
        functionSelector?: string,
        callData?: string,
    }>,
}
```

| Param | Type Info | Description |
|-|-|-|
| `hash` | Hex-string | Transaction or bundle hash. |
| `logs` | Array of JSON-encoded events | Event logs emitted by executing the transaction. |
| `txs` | Array of objects | Transactions from the event. If the event itself is a transaction, txs will only have one entry. Bundle events may have more. |
| `txs.to` | Hex-string | Transaction recipient address. |
| `txs.functionSelector` | Hex-string | 4-byte function selector. |
| `txs.callData` | Hex-string | Calldata of the transaction. |

## Stream Logic

Users subscribe to the stream by making an HTTP GET request on the stream endpoint.

The endpoint should send an event with the message `:ping` every 15 seconds if no other messages were sent in the last 15 seconds.
