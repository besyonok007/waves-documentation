# Sponsorship transaction binary format

## Transaction version 1

| Field order number | Field | JSON field name  | Field type | Field size in bytes | Comment |
| :--- | :--- | :--- | :--- | :--- | :--- |
| 1 | Version flag | | [Byte](/blockchain/blockchain/blockchain-data-types.md) | 1 | Indicates the [transaction version](/blockchain/transaction/transaction-version.md) is version 2 or higher.<br>Value must be 0 |
| 2 | [Transaction type ID](/blockchain/transaction-type.md) | type | [Byte](/blockchain/blockchain/blockchain-data-types.md) | 1 | Value must be 14 |
| 3 | [Transaction version](/blockchain/transaction/transaction-version.md) | version | [Byte](/blockchain/blockchain/blockchain-data-types.md) | 1 | Value must be 1 |
| 4 | Public key of the transaction sender  | senderPublicKey | Array[[Byte](/blockchain/blockchain/blockchain-data-types.md)] | 32 | |
| 5 | [Token ID](/blockchain/token/token-id.md) | assetId | Array[[Byte](/blockchain/blockchain/blockchain-data-types.md)] | 32 | |
| 6 | Minimal sponsor token fee | minSponsoredAssetFee | [Long](/blockchain/blockchain/blockchain-data-types.md) | 8 | |
| 7 | [Transaction fee](/blockchain/transaction/transaction-fee.md) | fee | [Long](/blockchain/blockchain/blockchain-data-types.md) | 8 | |
| 8 | [Transaction timestamp](/blockchain/transaction/transaction-timestamp.md) | timestamp | [Long](/blockchain/blockchain/blockchain-data-types.md) | 8 | |
| 9 | [Transaction proofs](/blockchain/transaction/transaction-proof.md) | proofs | [Proofs](/blockchain/transaction/transaction-proof.md) | `S` | If the array is empty, then `S` = 3. <br>If the array is not empty, then `S` = 3 + 2 × `N` + (`P`<sub>1</sub> + `P`<sub>2</sub> + ... + `P`<sub>n</sub>), where `N` is the number of proofs in the array, `P`<sub>n</sub> is the size on `N`-th proof in bytes. <br>The maximum number of proofs in the array is 8. The maximum size of each proof is 64 bytes |

## JSON representation of the transaction

See the [example](https://nodes.wavesnodes.com/transactions/info/7EL2XEGP1By427BeLcHPYeVnBzGsXen4egMAwQpWGBVR) in Node API.
