# Circuit

1. Write circom circuit
2. Compile the circuit:
   `circom simple_multiplier.circom --r1cs --wasm --sym`
3. Download a powers of tau trusted setup file
4. Run Plonk setup to get the proving key:
   `snarkjs plonk setup circuit.r1cs ptau_file.ptau proving_key.zkey`

To generate zkey:
`snarkjs plonk setup simple_multiplier/simple_multiplier.r1cs ptau/powersOfTau28_hez_final_08.ptau simple_multiplier/proving_key.zkey`

# Setup

Install [this](https://github.com/DanTehrani/circom-secq) fork of Circom that supports compiling to the secp256k1 base field.

```
git clone https://github.com/DanTehrani/circom-secq
```

```
cd circom-secq && cargo build --release && cargo install --path circom
```
