# AES Algorithm Implementation

This project is an implementation of the AES (Advanced Encryption Standard) algorithm in JavaScript. The implementation includes both encryption and decryption functionalities using the Rijndael block cipher. The algorithm is parameterized to use a block size of 128 bits and supports key sizes of 128, 192, or 256 bits.

## Features

- **Key Expansion**: Derives round keys from the initial secret key.
- **SubBytes**: Applies a non-linear substitution step using an S-Box.
- **ShiftRows**: Permutes the rows of the state matrix.
- **MixColumns**: Mixes the columns of the state matrix using matrix multiplication.
- **AddRoundKey**: Combines the state with the round key using XOR.
- **Padding Support**: Adds and removes padding to ensure data aligns with block size.
- **Encryption and Decryption**: Supports the complete AES process for block data.

## Prerequisites

- Basic understanding of cryptography concepts.
- Node.js installed (for running the script in a local environment).

## Installation

1. Clone the repository:

   ```bash
   git clone https://github.com/Ishak-rav/aes.git
   ```

2. Navigate to the project directory:

   ```bash
   cd aes
   ```

3. Ensure you have a JavaScript runtime like Node.js installed.

## Usage

### Initialization

Create an instance of the AES class with a secret key:

```javascript
const aes = new AES("your-128-bit-key");
```

### Encryption

Encrypt plaintext using the `encrypt` method:

```javascript
const plaintext = "your-plaintext";
const encrypted = aes.encrypt(plaintext);
console.log("Encrypted:", encrypted);
```

### Decryption

Decrypt ciphertext using the `decrypt` method:

```javascript
const decrypted = aes.decrypt(encrypted);
console.log("Decrypted:", decrypted);
```

### Example

```javascript
const aes = new AES("2b7e151628aed2a6abf7158809cf4f3c");
const plaintext = "3243f6a8885a308d313198a2e0370734";

const encrypted = aes.encrypt(plaintext);
console.log("Encrypted:", encrypted);

const decrypted = aes.decrypt(encrypted);
console.log("Decrypted:", decrypted);
```

## Files

- `index.js`: Contains the AES implementation.
- `README.md`: Documentation of the project.

## How It Works

1. **Key Expansion**: Generates the necessary round keys.
2. **Initial Round**: Adds the initial round key to the state.
3. **Rounds**: Applies SubBytes, ShiftRows, MixColumns, and AddRoundKey for all but the last round.
4. **Final Round**: Skips the MixColumns step in the last round.
5. **Decryption**: Performs the reverse operations of encryption in reverse order.

## Notes

- The current implementation uses a block size of 128 bits and a 128-bit key.
- Padding is implemented to ensure plaintext aligns with block size.

## Limitations

- Only supports 128-bit keys.
- This implementation is for educational purposes and may not be suitable for production use.

---

Feel free to contribute or report issues to improve the implementation.
