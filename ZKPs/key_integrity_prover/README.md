# Key Integrity Prover

This proof attests:

 - The attestation public key is signed by the root key of the trusted hardware
 - The root key of the trusted hardware is signed by the correct vendor key
 

To generate the proof:
```sh
# Compile the proof using zokrates
$ zokrates compile -i integrity_prover.code

# Compute witness 
# The data is valid if ~out_0 == 11
$ cat integrity_prover_data.txt | zokrates compute-witness

# Trusted setup
$ zokrates setup

# Generate proof
$ zokrates generate-proof
```


Performance on my devices:

```
Number of constraints: 207423
Has generated 201112 points

Time consumption:
---
On Mac: 20.315s

zokrates compute-witness: 9.850s
6.48s user 0.35s system 69% cpu 9.850 total

zokrates generate-proof: 10.465s 
zokrates generate-proof  15.60s user 0.86s system 157% cpu 10.465 total

---
On Pixel3 (when running on Termux): 23.909s

zokrates compute-witness: 8.676s
5.04s user 1.22s system 72% cpu 8.676 total

zokrates generate-proof: 15.233s
37.79s user 1.02s system 254% cpu 15.233 total
```