
# Post-Quantum Crypto: Module-Lattice-Based Key-Encapsulation Mechanism (ML-KEM) Implementation

## Description
The implementation of ML-KEM Standard, one of the three Federal Information Processing Standards (FIPS) approved for post-quantum cryptography. 
This standard is specified in [NIST FIPS 203](https://csrc.nist.gov/pubs/fips/203/final).
For this project, the FIPS 203 standard has been implemented for use in a cryptographic library



## Background
A key-encapsulation mechanism (KEM) is a set of algorithms that, under specific conditions, enable two parties to establish a shared secret key over a public channel.

The securely established shared key can then be utilized with symmetric-key cryptographic algorithms to perform fundamental tasks in secure communications, such as encryption and authentication.

Although quantum computers are not yet fully realized, they are believed to have the potential to break existing cryptographic standards. In anticipation of this, NIST has approved three new standards for post-quantum cryptography to ensure the world is prepared when quantum computers become a reality.

Currently, ML-KEM is considered secure, even against adversaries equipped with large-scale, fault-tolerant quantum computers. This standard defines the algorithms and parameter sets for the ML-KEM scheme:

• The three parameter sets, listed in order of increasing security strength and decreasing performance, are: **ML-KEM-512, ML-KEM-768, and ML-KEM-1024**.
• The key exchange algorithms specified are: **ML-KEM.KeyGen, ML-KEM.Encaps, and ML-KEM.Decaps**.


## How the standard has been implemented
All the sub-algorithms have been implemented as functions in Python to realize the three main algorithms: **ML-KEM.KeyGen, ML-KEM.Encaps, and ML-KEM.Decaps**. The parameter sets: **ML-KEM-512, ML-KEM-768, and ML-KEM-1024** have also been well-defined, allowing users to easily select their desired parameter set based on desired security and performance level.


## Algorithms
ML-KEM operates with three algorithms: 
• **ML-KEM.KeyGen**
Using internally generated randomness and requiring no input, the **ML-KEM.KeyGen** algorithm produces an **encapsulation key** and a **decapsulation key**. The encapsulation key can be made public, while the decapsulation key shall remain private.

• **ML-KEM.Encaps**
The **ML-KEM.Encaps** algorithm accepts an encapsulation key as input, generates randomness internally, and outputs a **ciphertext** and a **shared key**. 

• **ML-KEM.Decaps**
The **ML-KEM.Decaps** algorithm accepts a decapsulation key and an ML-KEM ciphertext as input, uses no randomness, and outputs a shared secret key.



## Parameter Sets
To instantiate ML-KEM, one must select a parameter set. Each parameter set is associated with a particular trade-off between security and performance. The three possible parameter sets are explained below:
• ML-KEM-512 (security category 1)
• ML-KEM-768 (security category 3)
• ML-KEM-1024 (security category 5)



## How to use the product
1. Install with `pip install quantumcrypto`. View Project Site [here](https://pypi.org/project/quantumcrypto/)

2. import the parameter sets
```python
from quantumcrypto.utils.parameters import P512, P768, P1024
```

3. import the functions
```python
from quantumcrypto.utils.functions import ml_kem_gey_gen, ml_kem_encaps, ml_kem_decaps
```

4. Select a parameter set. If none is selected, the strongest parameter set (P1024) is used by default.

5. Proceed to generate keys using the specified algorithms.

    - use as described in [ml_kem.py](quantumcrypto/ml_kem.py)


## How to contribute to the project





