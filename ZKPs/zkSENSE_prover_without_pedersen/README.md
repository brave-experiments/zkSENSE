# zkSENSE Prover without Pedersen Hash Verification

This proof attests:

 - all features are correctly calculated 
 - SVM components are correct calculated
 
Having these SVM components, correct SVM result can be reconstructed from the app. 

*This proof does not use Min/Max as features.*

To generate the proof:
```sh
# Compile the proof using zokrates
$ zokrates compile -i zkSENSE_prover.code

# Compute witness 
# The data is valid if ~out_0 == 11
$ cat zkSENSE_prover_data.txt | zokrates compute-witness

# Trusted setup
$ zokrates setup

# Generate proof
$ zokrates generate-proof
```


Performance on my devices:

```
---
On Mac: 117.315s

zokrates compute-witness: 66.16s
56.95s user 1.44s system 88% cpu 1:06.16 total

zokrates generate-proof: 51.155s
69.69s user 4.03s system 144% cpu 51.155 total

---
On Pixel3 (Termux): 169.912s

zokrates compute-witness: 54.402s
44.04s user 4.67s system 89% cpu 54.402 total

zokrates generate-proof: 115.51s
167.03s user 21.14s system 162% cpu 1:55.51 total

---
On Pixel3 (Android NDK): 217.305s
```