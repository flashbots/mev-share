# About

This document provides a set of example bundles and their expected execution results.

Tests can be found in the file [test.json](./test.json), where the test suite's JSON object is described.

## Preparing State

The transactions in the bundles expect the blockchain state to be set to state in the `genesisAlloc` field.

## Preparing the Block State

Each test case must be applied on top of a fresh block with the state described above and the header set to the value of the `header` field.

Relevant values from the header include:

* `number` - block number
* `gasLimit` - block gas limit
* `miner` - builder's address
* `baseFeePerGas` - base fee per gas


## Applying Test Bundles

Individual tests are objects within the `tests` array and include the following fields:

* `name` - a short test description
* `bundle` - the bundle to be executed
* `shouldFail` - set to true if the bundle is expected to fail
* `extractedRefunds` - an array of extracted values from the backruns in the bundle

### How to Interpret extractedRefunds

The exact method of paying kickbacks may vary from builder to builder. 
Some may use one transaction per kickback, while others may use a contract to batch multiple payments.

Different payment methods will yield slightly different kickback values. 
Instead of providing an exact kickback amount, we offer a value extracted by a backrun, 
the percentage of the value to be used for refunds, and a refund split to be potentially divided among multiple recipients.

The `extractedRefunds` array contains the following information for each backrun:

* `value` - values paid to the builder by the kickback
* `percent` - percentage of the value to be used for refunds
* `refundSplit` - an object that maps an address to the percentage of the refund to be paid to that address

Example:
```json
{
  "extractedRefunds": [
    {
      "value": "0x1636110e9abbc00",
      "percent": 90,
      "refundSplit": {
        "0xc87037874aed04e51c29f582394217a0a2b89d80": 100
      }
    }
  ]
}
```
In this example, 100030342000000000 wei is paid to the builder by the backrun, 
and 90% of that value should be used for refunds. 
100% of the refund value should be paid to the address 0xc87037874aed04e51c29f582394217a0a2b89d80.

To calculate the exact refund value, we must factor in the kickback transaction cost, 
which depends on the specific details of the kickback implementation. 

Let's assume that we take 30_000 * BASE_FEE * NUM_RECIPIENTS from the refund value upfront, 
and then take 90% of the remaining value and split it between the refund recipients.

For a base fee of 200 gwei and 1 recipient, we get:
```
refund = 100030342000000000 - 30000 * 200000000000 * 1 = 94030342000000000
kickback-tx-value = 94030342000000000 * 90% * 100% = 84627307800000000
```

The builder's refund transaction will have `tx.value = kickback-tx-value`
