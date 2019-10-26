# zkSENSE Prover

This proof attests:

 - sensor outputs match Pedersen hash
 - all features are correctly calculated 
 - the SVM component is correct calculated
 
Having the SVM component, correct SVM result can be reconstructed from the app. 

*This proof does not use Amplitude/Min/Max as features.*

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
Number of constraints: 675854
Has generated 480151 points

---
On Mac: 78.302s

zokrates compute-witness: 41.044s
33.80s user 1.14s system 85% cpu 41.044 total

zokrates generate-proof: 37.258s
58.07s user 3.08s system 164% cpu 37.258 total

---
On Pixel3 (Android NDK): 165.585s
```