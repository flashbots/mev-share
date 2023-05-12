{
  "genesisAlloc": {
    "0x3845794654dfec95145512fd33866dbc481893ea": {
      "balance": "0x0"
    },
    "0x3e7dfb3e26a16e3dbf6dfeeff8a5ae7a04f73aad": {
      "balance": "0xde0b6b3a7640000"
    },
    "0xc100000000000000000000000000000000000000": {
      "code": "0x6000351561000957fe5b600060006000600034416000f1",
      "balance": "0x0"
    },
    "0xc87037874aed04e51c29f582394217a0a2b89d80": {
      "balance": "0xde0b6b3a7640000"
    }
  },
  "header": {
    "parentHash": "0x0000000000000000000000000000000000000000000000000000000000000000",
    "sha3Uncles": "0x0000000000000000000000000000000000000000000000000000000000000000",
    "miner": "0x3845794654dfec95145512fd33866dbc481893ea",
    "stateRoot": "0x0000000000000000000000000000000000000000000000000000000000000000",
    "transactionsRoot": "0x0000000000000000000000000000000000000000000000000000000000000000",
    "receiptsRoot": "0x0000000000000000000000000000000000000000000000000000000000000000",
    "logsBloom": "0x00000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000",
    "difficulty": null,
    "number": "0x1",
    "gasLimit": "0x1c9c380",
    "gasUsed": "0x0",
    "timestamp": "0x0",
    "extraData": "0x",
    "mixHash": "0x0000000000000000000000000000000000000000000000000000000000000000",
    "nonce": "0x0000000000000000",
    "baseFeePerGas": "0x2e90edd000",
    "withdrawalsRoot": null,
    "hash": "0xf87a518fd4eec209b489cd38d510015b117d265ab1befde00588eac94c1e6696"
  },
  "tests": [
    {
      "name": "simple bundle",
      "bundle": {
        "version": "v0.1",
        "inclusion": {
          "block": "0x1"
        },
        "body": [
          {
            "tx": "0x02f86b0180843b9aca00852ecc889a0082520894c87037874aed04e51c29f582394217a0a2b89d808080c080a0a463985c616dd8ee17d7ef9112af4e6e06a27b071525b42182fe7b0b5c8b4925a00af5ca177ffef2ff28449292505d41be578bebb77110dfc09361d2fb56998260"
          }
        ],
        "validity": {}
      },
      "shouldFail": false
    },
    {
      "name": "bundle with reverting tx",
      "bundle": {
        "version": "v0.1",
        "inclusion": {
          "block": "0x1"
        },
        "body": [
          {
            "tx": "0x02f86b0180843b9aca00852ecc889a0082520894c87037874aed04e51c29f582394217a0a2b89d808080c080a0a463985c616dd8ee17d7ef9112af4e6e06a27b071525b42182fe7b0b5c8b4925a00af5ca177ffef2ff28449292505d41be578bebb77110dfc09361d2fb56998260"
          },
          {
            "tx": "0x02f86b0101843b9aca00852ecc889a008261a894c1000000000000000000000000000000000000008001c001a0bf350b29d1340b2f2074b8bb31f6869423b3577f9b858045f2fab49c144b7410a02e8c836f575f877d0a64a0b0252755caa1d1942daa1d58ed60c4ed7b40849be1"
          }
        ],
        "validity": {}
      },
      "shouldFail": true
    },
    {
      "name": "bundle with invalid tx (nonce mismatch)",
      "bundle": {
        "version": "v0.1",
        "inclusion": {
          "block": "0x1"
        },
        "body": [
          {
            "tx": "0x02f86b0180843b9aca00852ecc889a0082520894c87037874aed04e51c29f582394217a0a2b89d808080c080a0a463985c616dd8ee17d7ef9112af4e6e06a27b071525b42182fe7b0b5c8b4925a00af5ca177ffef2ff28449292505d41be578bebb77110dfc09361d2fb56998260"
          },
          {
            "tx": "0x02f86b0180843b9aca00852ecc889a0082520894c87037874aed04e51c29f582394217a0a2b89d808080c080a0a463985c616dd8ee17d7ef9112af4e6e06a27b071525b42182fe7b0b5c8b4925a00af5ca177ffef2ff28449292505d41be578bebb77110dfc09361d2fb56998260"
          }
        ],
        "validity": {}
      },
      "shouldFail": true
    },
    {
      "name": "bundle with reverting tx that is allowed to revert",
      "bundle": {
        "version": "v0.1",
        "inclusion": {
          "block": "0x1"
        },
        "body": [
          {
            "tx": "0x02f86b0180843b9aca00852ecc889a0082520894c87037874aed04e51c29f582394217a0a2b89d808080c080a0a463985c616dd8ee17d7ef9112af4e6e06a27b071525b42182fe7b0b5c8b4925a00af5ca177ffef2ff28449292505d41be578bebb77110dfc09361d2fb56998260"
          },
          {
            "tx": "0x02f86b0101843b9aca00852ecc889a008261a894c1000000000000000000000000000000000000008001c001a0bf350b29d1340b2f2074b8bb31f6869423b3577f9b858045f2fab49c144b7410a02e8c836f575f877d0a64a0b0252755caa1d1942daa1d58ed60c4ed7b40849be1",
            "canRevert": true
          }
        ],
        "validity": {}
      },
      "shouldFail": false
    },
    {
      "name": "bundle with invalid tx (nonce mismatch) that is allowed to revert",
      "bundle": {
        "version": "v0.1",
        "inclusion": {
          "block": "0x1"
        },
        "body": [
          {
            "tx": "0x02f86b0180843b9aca00852ecc889a0082520894c87037874aed04e51c29f582394217a0a2b89d808080c080a0a463985c616dd8ee17d7ef9112af4e6e06a27b071525b42182fe7b0b5c8b4925a00af5ca177ffef2ff28449292505d41be578bebb77110dfc09361d2fb56998260"
          },
          {
            "tx": "0x02f86b0180843b9aca00852ecc889a0082520894c87037874aed04e51c29f582394217a0a2b89d808080c080a0a463985c616dd8ee17d7ef9112af4e6e06a27b071525b42182fe7b0b5c8b4925a00af5ca177ffef2ff28449292505d41be578bebb77110dfc09361d2fb56998260",
            "canRevert": true
          }
        ],
        "validity": {}
      },
      "shouldFail": true
    },
    {
      "name": "bundle with backrun of tx",
      "bundle": {
        "version": "v0.1",
        "inclusion": {
          "block": "0x1"
        },
        "body": [
          {
            "tx": "0x02f86b0180843b9aca00852ecc889a0082520894c87037874aed04e51c29f582394217a0a2b89d808080c080a0a463985c616dd8ee17d7ef9112af4e6e06a27b071525b42182fe7b0b5c8b4925a00af5ca177ffef2ff28449292505d41be578bebb77110dfc09361d2fb56998260"
          },
          {
            "tx": "0x02f8730180843b9aca00852ecc889a008288b894c10000000000000000000000000000000000000088016345785d8a000080c001a07c8890151fed9a826f241d5a37c84062ebc55ca7f5caef4683dcda6ac99dbffba069108de72e4051a764f69c51a6b718afeff4299107963a5d84d5207b2d6932a4"
          }
        ],
        "validity": {
          "refund": [
            {
              "bodyIdx": 0,
              "percent": 90
            }
          ]
        }
      },
      "shouldFail": false,
      "extractedRefunds": [
        {
          "value": "0x1636110e9abbc00",
          "percent": 90,
          "refundSplit": {
            "0xc87037874aed04e51c29f582394217a0a2b89d80": 100
          }
        }
      ]
    },
    {
      "name": "bundle with backrun of bundle",
      "bundle": {
        "version": "v0.1",
        "inclusion": {
          "block": "0x1"
        },
        "body": [
          {
            "bundle": {
              "version": "v0.1",
              "inclusion": {
                "block": "0x1"
              },
              "body": [
                {
                  "tx": "0x02f86b0180843b9aca00852ecc889a0082520894c87037874aed04e51c29f582394217a0a2b89d808080c080a0a463985c616dd8ee17d7ef9112af4e6e06a27b071525b42182fe7b0b5c8b4925a00af5ca177ffef2ff28449292505d41be578bebb77110dfc09361d2fb56998260"
                },
                {
                  "tx": "0x02f86b0101843b9aca00852ecc889a0082520894c87037874aed04e51c29f582394217a0a2b89d808080c080a0ae5cf1bda12d0b4a51abb35fe716254ab4bbfaeb48cc1851662cef0f20bb43eea03e1fce95aed8e8607d8e26eea91f1fa22ede8f92c8d0335944a4850aaadc37bb"
                }
              ],
              "validity": {}
            }
          },
          {
            "tx": "0x02f8730180843b9aca00852ecc889a008288b894c10000000000000000000000000000000000000088016345785d8a000080c001a07c8890151fed9a826f241d5a37c84062ebc55ca7f5caef4683dcda6ac99dbffba069108de72e4051a764f69c51a6b718afeff4299107963a5d84d5207b2d6932a4"
          }
        ],
        "validity": {
          "refund": [
            {
              "bodyIdx": 0,
              "percent": 90
            }
          ]
        }
      },
      "shouldFail": false,
      "extractedRefunds": [
        {
          "value": "0x1636110e9abbc00",
          "percent": 90,
          "refundSplit": {
            "0xc87037874aed04e51c29f582394217a0a2b89d80": 100
          }
        }
      ]
    },
    {
      "name": "bundle with backrun of bundle with refund config",
      "bundle": {
        "version": "v0.1",
        "inclusion": {
          "block": "0x1"
        },
        "body": [
          {
            "bundle": {
              "version": "v0.1",
              "inclusion": {
                "block": "0x1"
              },
              "body": [
                {
                  "tx": "0x02f86b0180843b9aca00852ecc889a0082520894c87037874aed04e51c29f582394217a0a2b89d808080c080a0a463985c616dd8ee17d7ef9112af4e6e06a27b071525b42182fe7b0b5c8b4925a00af5ca177ffef2ff28449292505d41be578bebb77110dfc09361d2fb56998260"
                },
                {
                  "tx": "0x02f86b0101843b9aca00852ecc889a0082520894c87037874aed04e51c29f582394217a0a2b89d808080c080a0ae5cf1bda12d0b4a51abb35fe716254ab4bbfaeb48cc1851662cef0f20bb43eea03e1fce95aed8e8607d8e26eea91f1fa22ede8f92c8d0335944a4850aaadc37bb"
                }
              ],
              "validity": {
                "refundConfig": [
                  {
                    "address": "0xc87037874aed04e51c29f582394217a0a2b89d80",
                    "percent": 50
                  },
                  {
                    "address": "0x3e7dfb3e26a16e3dbf6dfeeff8a5ae7a04f73aad",
                    "percent": 50
                  }
                ]
              }
            }
          },
          {
            "tx": "0x02f8730180843b9aca00852ecc889a008288b894c10000000000000000000000000000000000000088016345785d8a000080c001a07c8890151fed9a826f241d5a37c84062ebc55ca7f5caef4683dcda6ac99dbffba069108de72e4051a764f69c51a6b718afeff4299107963a5d84d5207b2d6932a4"
          }
        ],
        "validity": {
          "refund": [
            {
              "bodyIdx": 0,
              "percent": 90
            }
          ]
        }
      },
      "shouldFail": false,
      "extractedRefunds": [
        {
          "value": "0x1636110e9abbc00",
          "percent": 90,
          "refundSplit": {
            "0x3e7dfb3e26a16e3dbf6dfeeff8a5ae7a04f73aad": 50,
            "0xc87037874aed04e51c29f582394217a0a2b89d80": 50
          }
        }
      ]
    },
    {
      "name": "bundle with backrun of backrun of user tx",
      "bundle": {
        "version": "v0.1",
        "inclusion": {
          "block": "0x1"
        },
        "body": [
          {
            "bundle": {
              "version": "v0.1",
              "inclusion": {
                "block": "0x1"
              },
              "body": [
                {
                  "tx": "0x02f86b0180843b9aca00852ecc889a0082520894c87037874aed04e51c29f582394217a0a2b89d808080c080a0a463985c616dd8ee17d7ef9112af4e6e06a27b071525b42182fe7b0b5c8b4925a00af5ca177ffef2ff28449292505d41be578bebb77110dfc09361d2fb56998260"
                },
                {
                  "tx": "0x02f8730180843b9aca00852ecc889a008288b894c10000000000000000000000000000000000000088016345785d8a000080c001a07c8890151fed9a826f241d5a37c84062ebc55ca7f5caef4683dcda6ac99dbffba069108de72e4051a764f69c51a6b718afeff4299107963a5d84d5207b2d6932a4"
                }
              ],
              "validity": {
                "refund": [
                  {
                    "bodyIdx": 0,
                    "percent": 90
                  }
                ],
                "refundConfig": [
                  {
                    "address": "0x3e7dfb3e26a16e3dbf6dfeeff8a5ae7a04f73aad",
                    "percent": 100
                  }
                ]
              }
            }
          },
          {
            "tx": "0x02f8730101843b9aca00852ecc889a008288b894c10000000000000000000000000000000000000088016345785d8a000080c001a0650c394d77981e46be3d8cf766ecc435ec3706375baed06eb9bef21f9da2828da064965fdf88b91575cd74f20301649c9d011b234cefb6c1761cc5dd579e4750b1"
          }
        ],
        "validity": {
          "refund": [
            {
              "bodyIdx": 0,
              "percent": 80
            }
          ]
        }
      },
      "shouldFail": false,
      "extractedRefunds": [
        {
          "value": "0x1636110e9abbc00",
          "percent": 90,
          "refundSplit": {
            "0xc87037874aed04e51c29f582394217a0a2b89d80": 100
          }
        },
        {
          "value": "0x1636110e9abbc00",
          "percent": 80,
          "refundSplit": {
            "0x3e7dfb3e26a16e3dbf6dfeeff8a5ae7a04f73aad": 100
          }
        }
      ]
    }
  ]
}