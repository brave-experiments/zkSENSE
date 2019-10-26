# Zero Knowledge Proofs (ZKPs)
This folder includes proofs to calculate the precomputation made to the data before including it in the ML model and a proof of pre image of a pedersen hash.

To compute the running time of proving pre-image of a pedersen hash run the following commands:

`zokrates compile -i pedersen_commitment.code`

`cat pedersen_data | zokrates compute-witness`

`zokrates setup`

`time zokrates generate-proof`

To compute the running times of proving the precomputations of the sensor data, run the following: 

`zokrates compile -i proofs_on_input`

`cat data | zokrates compute-witness`

`zokrates setup`

`time zokrates generate-proof`


The last file evaluates all the computations (including max and min). To calculate the time of the proof generation without the max/min calculations, comment out (//) the corresponding lines in file proofs_on_input
