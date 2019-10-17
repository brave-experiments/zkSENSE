# zkSENSE Prover
___

This proof attests:

 - sensor outputs match Pedersen hash
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
Number of constraints: 1546406
Has generated 1348326 points

Time consumption:
---
On Mac: 214.35s

zokrates compute-witness: 113.54s
86.86s user 3.13s system 79% cpu 1:53.54 total

zokrates generate-proof: 100.81s
135.55s user 8.81s system 143% cpu 1:40.81 total

---
On Pixel3 (when running on root shell): 202.95s

zokrates compute-witness: 91.14s
1m31.14s real     1m04.98s user     0m09.05s system

zokrates generate-proof: 111.81s 
1m51.81s real     2m47.66s user     0m18.69s system
```