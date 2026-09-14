# Document commitment 001

Deposited by Stephan Lauermann. Version: `deposit-001-v1`.

This deposit contains an encrypted document (`proof.pdf.age`), SHA-256
checksums of the original and encrypted files, and `COMMITMENT.txt`.
The original document and the dedicated decryption
key are retained privately for possible later release.

The exact commitment is in `COMMITMENT.txt`. Its preparation time is
self-reported. This commitment identifies exact bytes; it does not establish
authorship, correctness or priority. No independent timestamp is included
in this release.

## Verify the encrypted download

Download the release assets into a fresh folder and run:

```sh
shasum -a 256 -c ciphertext.sha256
```

## Verify a later disclosure

If the original `proof.pdf` is released, verify it against `plaintext.sha256`.
If the dedicated key is released as `identity.txt`, use
[age](https://github.com/FiloSottile/age) to decrypt the deposited file in a
fresh folder, where `proof.pdf` does not already exist:

```sh
shasum -a 256 -c ciphertext.sha256
age --decrypt --identity identity.txt --output proof.pdf proof.pdf.age
shasum -a 256 -c plaintext.sha256
```

A revised document requires a new version and a new commitment. This deposit
identifies only the exact original bytes specified by its checksum.
