# Readme
---

This folder contains implementation for the proof of the validity of the attestation key and the proof of the pre-image of sha256 hashes.

The former is implemented in `integrity_prover.code` with test data in `integrity_prover_data.txt`. Proof generation takes around 8.5s on my Macbook.

The latter is implemented in `sha256_prover.code` with test data in `sha256_prover_data.txt`.

For the latter, the performance data on my devices is:

```
On Mac: 49.703s
zokrates generate-proof  62.56s user 5.31s system 136% cpu 49.703 total


On Pixel3: 81.02s
zokrates generate-proof  144.54s user 7.11s system 187% cpu 1:21.02 total
```

Comparison between simple SHA256 (`playground/sha256_prover_simple.code`) and pederson (`../ZKPs/pedersen_commitment.code`):

```
SHA256 Simple (on Mac):
zokrates generate-proof  3.44s user 0.21s system 163% cpu 2.238 total

Pederson Commitment (on Mac):
zokrates generate-proof  5.52s user 0.18s system 227% cpu 2.512 total

```

*Note: Zokrates has a weird bug that when comparing result with 1 or 0, it always passes the check no matter what the input is. Therefore, I changed the return to 11 or 10 in the `modules/verify_pk_root.code`.*