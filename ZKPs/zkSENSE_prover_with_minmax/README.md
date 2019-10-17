# zkSENSE Prover with Min & Max
___

This proof attests:

 - sensor outputs match Pedersen hash
 - all features are correctly calculated 
 - SVM components are correct calculated
 
Having these SVM components, correct SVM result can be reconstructed from the app. 

*This proof uses Min & Max as features.*

To generate the proof:
```sh
# Compile the proof using zokrates
$ zokrates compile -i zkSENSE_with_minmax_prover.code

# Compute witness 
# The data is valid if ~out_0 == 11
$ cat zkSENSE_with_minmax_prover_data.txt | zokrates compute-witness

# Trusted setup
$ zokrates setup

# Generate proof
$ zokrates generate-proof
```


Performance on my devices:

```
Number of constraints: 2467830
Has generated 2260694 points

Time consumption:
---
On Mac: 451.68s

zokrates compute-witness: 196.35s
148.40s user 6.39s system 78% cpu 3:16.35 total

zokrates generate-proof: 255.33s 
user 16.97s system 146% cpu 3:05.81 total

---
On Pixel3 (when running on root shell): UNKNOWN

zokrates compute-witness: 141.62s
2m21.62s real     1m45.76s user     0m19.25s system

zokrates generate-proof: system crash 
```