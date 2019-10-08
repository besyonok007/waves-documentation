# ByteVector

The **ByteVector** is a keyword of the byte array [data type](/ride/data-types.md).

The maximum size of the variable of the byte array data type is 65,536 bytes.

The variable of the byte array data type is assigned a value using one of the literals: `base16`, `base58` or `base64`. The literal name in single quotes is followed by a string in [Base16](https://en.wikipedia.org/wiki/Hexadecimal#Base16_&#40;Transfer_encoding&#41;), [Base58](https://en.wikipedia.org/wiki/Base58) or [Base64](https://en.wikipedia.org/wiki/Base64).

## Examples

``` ride
let a = base16'52696465'
let b = base58'8t38fWQhrYJsqxXtPpiRCEk1g5RJdq9bG5Rkr2N7mDFC'
let c = base64'UmlkZQ=='
```
