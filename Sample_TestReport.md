| Test Case ID | Test Data | Test Steps | Expected Output | RESULT |
|--------------|-----------|------------|-----------------|--------|
| 1 | Hex String: `0x0123456789abcdef0123456789abcdef0123456789abcdef0123456789abcdef` | Create an instance of `Ed25519PublicKey` using a hex string. | Instance is created without error, and `toString()` returns the original hex string. | :x: FAIL |
| 2 | Uint8Array: `[1, 35, 69, 103, ...]` | Create an instance of `Ed25519PublicKey` using a Uint8Array. | Instance is created without error, and `toUint8Array()` returns the original Uint8Array. | :+1: PASS |
| 3 | Invalid Hex Input: `0123456789abcdef` | Attempt to create an instance of `Ed25519PublicKey` with an invalid hex input length. | Throws an error indicating the public key length should be 32 bytes. | :+1: PASS |
| 4 | Valid Signature: `ed25519.signatureHex`, Message: `ed25519.messageEncoded` | Verify a correct signature using `Ed25519PublicKey`. | Returns `true` indicating the signature is valid. | :+1: PASS |
| 5 | Incorrect Signed Message | Verify an incorrect signature using `Ed25519PublicKey`. | Returns `false` indicating the signature is invalid. | :+1: PASS |
| 6 | Malleable Signature | Check for malleable signatures using `Ed25519Signature`. | Returns `false` indicating the signature is not canonical. | :+1: PASS |
| 7 | Serialized Public Key | Serialize a public key using `Serializer` and then compare the output. | Serialized output matches the expected Uint8Array. | :x: FAIL |
| 8 | Serialized Private Key | Serialize a private key using `Serializer` and then compare the output. | Serialized output matches the expected Uint8Array. | :+1: PASS |
| 9 | Generate Random Private Key | Generate a new random `Ed25519PrivateKey`. | A new private key instance is created successfully, and it is different from any previously generated keys. | :+1: PASS |
| 10 | Derive Public Key from Private Key | Derive a public key from an existing `Ed25519PrivateKey`. | The derived public key matches the expected public key string. | :+1: PASS |
