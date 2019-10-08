# Byte array functions

|#|Name | Description | Complexity |
|:---| :--- | :--- | :--- |
|1| [drop(ByteVector, Int): ByteVector](#drop) | Returns the byte array without the first `N` bytes | 1 |
|2| [dropRight(ByteVector, Int): ByteVector](#drop-right) | Returns the byte array without the last `N` bytes | 19 |
|3| [size(ByteVector): Int](#size) | Returns the number of bytes in the byte array | 1 |
|4| [take(ByteVector, Int): ByteVector](#take) | Returns the first `N` bytes of the byte array | 1 |
|5| [takeRight(ByteVector, Int): ByteVector](#take-right) | Returns the last `N` bytes of the byte array | 19 |

## drop(ByteVector, Int): ByteVector<a id="drop"></a>

Returns the byte array without the first `N` bytes.

``` ride
drop(xs: ByteVector, number: Int): ByteVector
```

### Parameters

#### `xs`: [ByteVector](/ride/data-types/byte-vector.md)

Byte array.

#### `number`: [Int](/ride/data-types/int.md)

Number `N`.

## dropRight(ByteVector, Int): ByteVector<a id="drop-right"></a>

Returns the byte array without the last `N` bytes.

``` ride
dropRight(xs: ByteVector, number: Int): ByteVector
```

### Parameters

#### `xs`: [ByteVector](/ride/data-types/byte-vector.md)

Byte array.

#### `number`: [Int](/ride/data-types/int.md)

Number `N`.

## size(ByteVector): Int<a id="size"></a>

Returns the number of bytes in the byte array.

``` ride
size(byteVector: ByteVector): Int
```

### Parameters

#### `byteVector`: [ByteVector](/ride/data-types/byte-vector.md)

Byte array.

## take(ByteVector, Int): ByteVector<a id="take"></a>

Returns the first `N` bytes of the byte array.

``` ride
take(xs: ByteVector, number: Int): ByteVector
```

### Parameters

#### `xs`: [ByteVector](/ride/data-types/byte-vector.md)

Byte array.

#### `number`: [Int](/ride/data-types/int.md)

Number `N`.

## takeRight(ByteVector, Int): ByteVector<a id="take-right"></a>

Returns the last `N` bytes of the byte array.

``` ride
takeRight(xs: ByteVector, number: Int): ByteVector
```

### Parameters

#### `xs`: [ByteVector](/ride/data-types/byte-vector.md)

Byte array.

#### `number`: [Int](/ride/data-types/int.md)

Number `N`.
