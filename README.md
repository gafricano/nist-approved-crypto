# Comprehensive List of NIST-Approved Cryptographic Algorithms and Modes of Operation
Since I found hard to have a single place with a list of NIST-Approved Cryptographic Algorithms and Operations Mode I made this list to facilitate my own life or maybe for someone else too. An interesting page to follow-up with document revisions is here [Crypto Publication Review Project](https://csrc.nist.gov/Projects/crypto-publication-review-project)

Last update: 06/Dec/2024


## 1. Symmetric Encryption Algorithms and Modes of Operation 
### Advanced Encryption Standard (AES) :green_circle: : 
A symmetric key algorithm standardized in [FIPS 197](https://nvlpubs.nist.gov/nistpubs/FIPS/NIST.FIPS.197-upd1.pdf) 
Supported key sizes:
- 128 bits
- 192 bits
- 256 bits
  
#### Modes of Operation:
- Cipher Block Chaining (CBC): Recommended when used with proper padding. :orange_circle:
- Counter (CTR): Converts block ciphers into stream ciphers.
- Galois/Counter Mode (GCM): Provides authenticated encryption.
- Cipher Feedback (CFB): Supports variable block sizes.
- Output Feedback (OFB): Ensures no ciphertext expansion.
- XTS-AES Mode: Recommended for disk encryption ([SP 800-38E](https://doi.org/10.6028/NIST.SP.800-38E) and revision note form Feb 2024 for monitoring here [Revision Note for 800-38E](https://csrc.nist.gov/News/2024/nist-to-revise-special-publication-80038e)).
- Standardized in [FIPS 197](https://doi.org/10.6028/NIST.FIPS.197-upd1) and [SP 800-38](https://doi.org/10.6028/NIST.SP.800-38E) series.

#### Modes Deprecated or not recommended
- Electronic Codebook (ECB): Deprecated for new systems due to vulnerabilities.
- NIST does not officially deprecate CBC in general terms, but due to its vulnerabilities, its use in certain contexts and without proper safeguards is strongly discouraged. Combine CBC with a cryptographic integrity mechanism, like HMAC, to ensure authenticated encryption (e.g., Encrypt-then-MAC construction).

### Triple DES (3DES or TDEA) :red_circle::
Deprecated for all applications through 2023, and disallowed after December 31, 2023.
- [Withdarawn NIST Special Publication 800-67 Revision 2 ](https://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-67r2.pdf)
- [NIST Withdraw Note](https://csrc.nist.gov/news/2023/nist-to-withdraw-sp-800-67-rev-2).

Historically this symmetric key algorithm applies the DES cipher algorithm three times to each data block.

#### Modes of Operation:
- CBC: Widely used in legacy systems.
- ECB: Deprecated.
- CFB: Supports streaming-encryption.
- OFB: Ensures deterministic outputs.

#### Modes Deprecated or not recommended
See [NIST Withdraw Note](https://csrc.nist.gov/news/2023/nist-to-withdraw-sp-800-67-rev-2).


## 2. Hash Functions:
### SHA-1 :red_circle:
Not recommended any more.
Specified in [FIPS 180-4](https://nvlpubs.nist.gov/nistpubs/FIPS/NIST.FIPS.180-4.pdf).
Is a 160-bit hash function 

### SHA-2 :green_circle:
Specified in [FIPS 180-4](https://nvlpubs.nist.gov/nistpubs/FIPS/NIST.FIPS.180-4.pdf).
- SHA-224
- SHA-256
- SHA-384
- SHA-512
- SHA-512/224
- SHA-512/256.

### SHA-3 :green_circle:
Specified in [FIPS 202](https://nvlpubs.nist.gov/nistpubs/FIPS/NIST.FIPS.202.pdf) and revision note here []().
- SHA3-224
- SHA3-256
- SHA3-384
- SHA3-512.

## 3. Digital Signature Algorithms

## 4. Key Management and Establishment Algorithms

## 5. Message Authentication Codes (MACs)

## 6. Authenticated Encryption

## 7. Random Number Generators

## 8. Other Notable Cryptographic Functions
