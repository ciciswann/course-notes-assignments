# Week 2 Notes - Intro to Hash Functions for Password Handling

### Using Hash Functions to Secure Authentication
* Two schemes: naive and naive hash function
* Naive password handling: store user passwords and compare a user password submision to stored version before authentication
   * problems: if db is compromised then attacker has passwords, if not compromised internal org people have passwords, extra care needs to be taken when broadcasting password to compare it to database, bascially everything
* Naive hash function application: when a user enters a password, hash it and send the has to the server, compare this value to a stored hash
   * Problem: this set up is subject to what is called a rainbow attack - attacker can precompute all the hashes from common passwords
* Salt - data that is seemingly random. It's combined with other info before hashing. That way a salt would need to be known by an attacker in order to perform a rainbow attack
* Basic secure setup - let H be a hash function. we use | to represent concatenation. The user submit H(Password) to the server. The server then computes H(H(Password)|Salt) and compares that to a stored value.
* Appropriate use of salt for passwords - each user has their own salt, salts should allow enough entropy, salts provide entropy that humans don't usually apply to their password creation.
* other application of salts: compact blocks use an eight byte result for a hash to index transactions, the compact block protocol uses a salt to prevent an attacker creating collisions (birthday attack) during block propogation.
* some hash functions: SHA256, SHA512, RPEMD-160
* some key derivation function - PBKDF2 (password based key derivation function 2)
* some deprecated - md5, SHA1
* hash functions used by bitcoin - SHA256 (used to generate PoW, secure transaction in merkle tree), RPEMD-160 (used in addresses, public key does not need to be revealed to give someone an address)
* Protecting passwords - hash function choice
   * the function PBKDF2 - takes five args, two of those args tune how difficult this function is to compute, you can basically adjust the difficulty of brute forcing this function

### Side Channel Attacks
* To prove a crypto technique is secure you start with some assumptions that feed into the idea of a proof to then conclude whatever protocol your looking at is secure
* But, sometimes the attacker works outside of those assumptions (side channel attack) - something that wasn't considered in the proof
* side channel attack on bitcoin example - needs physical access to device (hardware wallet)
* ex. listen to sound of device to recover private key 
* ex. scripting attack on PGP
* zero day exploit
* The security of an Elliptic Curve Digital Signature Algorithm is dependent on the assumption that a particular discrete logarithm problem is sufficiently hard. The security is also dependent of the sufficiently random choice of two numbers. What is an example of a compromise that is not an example of a side channel attack?
   * A quantum computer is manufactured that can solve a discrete logarithm problem associated with an ECDSA.
* Side channel attacks do not always render crypto protocols insecure and unreliable

### Merkle Trees & Merkle Tree Proof Problem Walkthrough
![image](https://user-images.githubusercontent.com/17733481/160310981-fe8ad98a-ef6c-44b5-b56c-e25647d98aaa.png)
* Types: binary, tertiary

![image](https://user-images.githubusercontent.com/17733481/160311091-005bc465-26c8-4fd2-a6e6-6e658a3768ef.png)

* can be used to verify an object in a list without having available all the transactions
* easily broadcast - secure and efficient
