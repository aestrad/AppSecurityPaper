# Security Principles

## User Data Protection


## How vault items are secured


## Sharing Data between Users

It needs kind of an Organization Symmetric Key. It must be a Cryptographically Secure Preudorandom Number Generator (CSPRNG). The Symmetric Key is encrypted using the public key from a generated RSA Key Pair. 
The private key from the Generated RSA Key Pair is encrypted with Generated Symmetric Key using AES-256.

The Generated RSA Key Pair and Generated Symmetric Key were created at the setup.  


## Data Protectin in Transit

Data encrypted on the client. 

It must use TLS/SSL to secure communication between clients and servers. The TLS implementation must use 2048-bit X.509 certificates for server authentication and key exchange and a strong cipher suite for bulk 
encryption. **Reject weak ciphers and protocols**

It must also implement HTTP Security headers such as HTTP Strict Transport Security (HSTS), which will force all connections to use TLS. Protection against HTTP downgrade attacks (SSL stripping attacks).

## Data Protection at Rest

AES 256-bit encryption as well as PBKDF-SHA256 to secure data. PBKDF-SHA256 is used to derive the encryption key from a Master Password. Then this key is salted and hashed for authenticating with the servers. The default iteration count used with PBKDF2 is 100,001 iterations on the client (this client-side iteration count must be configurable), and then an additional 100,000 iterations when stored on the servers (for a total of 200,001 iterations by default). 

**end-to-end encryption**

In a TechRadar piece, author Christian Rigg noted,

> Zero knowledge refers to policies and architecture that eliminate the possibility for a password manager to access your password.

Bitwarden

> There are cases where software and service providers promote encryption but retain the key. These cases do not qualify as zero knowledge from our perspective since the software and service providers technically > have the ability to decrypt the data.

### Zero trust as a protective mindset
The zero trust model initially emerged as a way for organizations to get beyond the traditional thinking of internal and external threats to their IT operations. Today, companies need to protect from threats coming from both inside and outside. Zero trust models often use technologies like identity and access management, encryption, multi-factor authentication, and permissions to operate.

End to End encryption and zero knowledge https://bitwarden.com/blog/end-to-end-encryption-and-zero-knowledge
