# Encrypted document deposit

Deposit identifier: `deposit-002-v1`.

This deposit records 24 document versions without publishing their readable contents.
Each PDF is encrypted separately with age. The readable PDFs and decryption keys
are withheld. Neutral document identifiers are used.

`plaintext.sha256` lists the SHA-256 digests of the preserved PDFs.
`ciphertext.sha256` lists the digests of the encrypted files supplied here.
`COMMITMENT.txt` records both lists. A readable PDF disclosed later can be compared
with its original digest to establish whether it is the same deposited file.

Hashes establish file identity; they do not by themselves establish authorship,
mathematical correctness, or an independently certified timestamp.
