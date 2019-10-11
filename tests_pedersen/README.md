### Generating a Pedersen hash and proving knowledge of pre-image

We have a dummy set of 512 bits in `generated_bits`. First we can generate the hashed value of those bits by running the following commands: 

`zokrates compile -i compute_pedersen_hash.code`
`cat generated_bits | zokrates compute-witness`

The output of the witness computation is the hash value. Then we can prove that we know the pre-image to that hashed value

`zokrates compile -i compare_hash.code`
`cat try.txt | zokrates compute-witness`
`zokrates setup`
`zokrates generate-proof`

(Note that the hashed value is already hardcoded in our try.txt, so if you change the input, make sure to change the hashed value in try.txt)
