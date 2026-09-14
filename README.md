# Encrypted PDF deposit

Deposited by Stephan Lauermann.

This repository contains an encrypted PDF and SHA-256 checksums. The encrypted
PDF requires a decryption key, which is retained privately.

If the original PDF is disclosed later, its checksum can be compared with this
deposit to verify that it is the same file.

**Latest:** [v2](https://github.com/slauerma/hash/releases/tag/deposit-001-v2) ·
**Previous:** [v1](https://github.com/slauerma/hash/releases/tag/deposit-001-v1)

Original PDF SHA-256:

```text
682a43a774cad78ea3d68b6b362a998313d4668b794221b2d3099b95280fdd31
```

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

A revised document requires a new version and a new commitment. Each deposit
identifies only the exact original bytes specified by its checksum.
