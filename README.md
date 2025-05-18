# UOV Signature Scheme - Magma Implementation

This repository provides an implementation of the Unbalanced Oil and Vinegar (UOV) multivariate digital signature scheme in Magma, based on the specification submitted to NIST for post-quantum cryptography standardisation.

Reference: [UOV Specification - NIST Round 1](https://csrc.nist.gov/csrc/media/Projects/pqc-dig-sig/documents/round-1/spec-files/UOV-spec-web.pdf)


Overview

The UOV signature scheme is a post-quantum secure signature algorithm based on multivariate quadratic equations over a finite field. This implementation is intended for educational and verification purposes and is written in the Magma Computer Algebra System.

Unlike the NIST submission, this version uses Magma’s internal pseudorandom generator in place of SHA-256 for reproducibility using Magma’s online calculator. The given code can easily be adapted to the NIST submission by using SHA-256.

---

Features

- Finite field setup: GF(2^4)
- Generates:
  - Secret key matrix: O
  - Public key matrices: P1_i, P2_i, P3_i
- Signature generation using the secret key
- Signature verification using the public key
- Uses 128-bit seeds for determinism

---

Requirements

- [Magma](http://magma.maths.usyd.edu.au/magma/) (accessible via license or university access)
- You may have change the number of seed bits to less than 32 if the magma online calculator doesn't work


Usage

Run the program

1. Open your Magma environment or use [Magma Calculator](http://magma.maths.usyd.edu.au/calc/).
2. Copy and paste the full code from `uov_signature.m`.
3. Execution will:
   - Generate secret/public key components
   - Sign a hardcoded message `"0"`
   - Verify the signature

Expected output:
```plaintext
128-bit secret binary seed: ...
128-bit public binary seed: ...
"Signature is Valid"
