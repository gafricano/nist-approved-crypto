# Comprehensive List of NIST-Approved Cryptographic Algorithms and Modes of Operation
Since I found it hard to have a single place with a list of NIST-Approved Cryptographic Algorithms and Operations Modes I made this list to facilitate my own life or for someone else too. An interesting page to follow up with document revisions is here [Crypto Publication Review Project](https://csrc.nist.gov/Projects/crypto-publication-review-project)

Last update: 09/Dec/2024


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
- [Withdarawn NIST Special Publication 800-67 Revision 2 ](https://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-67r2.pdf) 🔴
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
### Digital Signature Algorithm (DSA) 🔴
- Standardized in the withdrawn [FIPS 186-4](https://doi.org/10.6028/NIST.FIPS.186-4).🔴
- Superseded by [FIPS-186-5](https://doi.org/10.6028/NIST.FIPS.186-5) which declares DSA as not approved anymore.
### Elliptic Curve Digital Signature Algorithm (ECDSA) 🟢
- Standardized in the withdrawn [FIPS 186-4](https://doi.org/10.6028/NIST.FIPS.186-4).
- Superseded by [FIPS-186-5](https://doi.org/10.6028/NIST.FIPS.186-5)
### RSA Digital Signature Scheme 🟢
- Referenced in [FIPS-186-5](https://nvlpubs.nist.gov/nistpubs/FIPS/NIST.FIPS.186-5.pdf)
- Based PKCS #1 v2.2 [RFC 8017](https://www.rfc-editor.org/rfc/rfc8017)
### Edwards-Curve Digital Signature Algorithm (EdDSA)
- Based on [FIPS-186-5](https://nvlpubs.nist.gov/nistpubs/FIPS/NIST.FIPS.186-5.pdf)
- For Ed25519, SHA-512 shall be used.
- For Ed448, SHAKE256 (as specified in FIPS 202) shall be used.

## 4. Key Management and Establishment Algorithms
### RSA Key Exchange 🟢
- Defined in SP [800-56B rev.2](https://doi.org/10.6028/NIST.SP.800-56Br2)
### Diffie-Hellman (DH) 🟢
- Defined in [SP 800-56A rev.3](https://doi.org/10.6028/NIST.SP.800-56Ar3).
### Elliptic Curve Diffie-Hellman (ECDH) 🟢
- Defined in [SP 800-56A rev.3](https://doi.org/10.6028/NIST.SP.800-56Ar3).

## 5. Message Authentication Codes (MACs)
### HMAC (Hash-Based Message Authentication Code) 🟢
- Defined in [FIPS 198-1](https://doi.org/10.6028/NIST.FIPS.198-1) and is going to be withdrawn when NIST SP 800-224 is published🟡
- Initial Public Draft (IPD) [SP 800-224](https://doi.org/10.6028/NIST.SP.800-224.ipd) notes in the following NIST page [Announcement 800-224 IDP](https://csrc.nist.gov/pubs/sp/800/224/ipd)
### CMAC (Cipher-based Message Authentication Code) 🟢
- Defined in SP [800-38B](https://doi.org/10.6028/NIST.SP.800-38B) which is being reviewed. 🟡
- [SP 800-224 announcement page](https://csrc.nist.gov/pubs/sp/800/38/b/upd1/final)

## 6. Authenticated Encryption
### AES-GCM (Galois/Counter Mode) 🟢
- Provides encryption and authentication in a single step.
- Defined in [SP 800-38D](https://doi.org/10.6028/NIST.SP.800-38D) and is being revised see [Announcement page](https://csrc.nist.gov/News/2024/nist-to-revise-sp-80038d-gcm-and-gmac-modes). 🟡
### AES-CCM (Counter with CBC-MAC) 🟢
- Combines counter mode encryption with CBC-MAC for authentication.
- Defined in SP [800-38C](https://doi.org/10.6028/NIST.SP.800-38C) and if being revised see [Announcement page](https://csrc.nist.gov/News/2024/nist-to-revise-sp-80038d-gcm-and-gmac-modes).🟡
- 
## 7. Random Number Generators
### Deterministic Random Bit Generators (DRBGs) 🟢
- Based on cryptographic hash functions, block ciphers, or elliptic curves.
- Defined in [SP 800-90A rev.1](https://doi.org/10.6028/NIST.SP.800-90Ar1).

## 8. Other Notable Cryptographic Functions
