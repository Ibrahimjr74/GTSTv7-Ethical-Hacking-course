
## what is Cryptography

- Is the science of secret or expressing something in hidden manner
- Used to secure data
- it mainly consists of two components
         -  Practice of hiding message so that they can not be read by any one other than intended recipient
         - Integrity that users of data resource are not read or altered.
    **Cipher
    - Cipher is a method for encrypting messages
    - Encryption algorithms are standard & published , the key is an algorithm 
    - key is a string of numbers or characters
    - if same key is used for encryption & decryption the algorithm is called symmetric. like Caesar Cipher , AES DES
    - if the keys used for encryption & decryption the algorithm  are different is called symmetric.
    - Types : Block Cipher     |        Stream Cipher
    - Substitution Ciphers
            -   Caesar Cipher is a method in which each letter in the alphabet is rotated by three letters.
    - Shift Cipher
             - shifts the letter that are not found on the string that will be encrypted.
        ### Data Encryption Standard / DES
        - works on 64 bit blocks, first developed by IBM uses the key algorithm
		- DES is a block cipher that processes data in fixed-size blocks of 64 bits. 
    
		- DES uses a 56-bit key for encryption. 
	    - Although the key is technically 64 bits, 8 of those bits are used for parity (error checking) and do not contribute to the security of the key. 

		- DES is no longer considered secure for protecting sensitive information and has been officially withdrawn as a standard by NIST.
    

**
### Initial and Final Permutation
- The initial final permutations are straight permutation boxes that are inverse of each 
	other. The decryption is the inverse process.

-**The Feistel structure splits the 64-bit block of plaintext into two equal halves: a left half (L) and a right half (R).**
The encryption process consists of 16 rounds , where the two halves of the blocks are processed and swapped iteratively.

- Each round involves several key operations:
- Expansion
- Substitution
- Permutation
- XOR with a subkey
- Swapping halves
#### How AES works ?
![[Pasted image 20240904204602.png]]
### Limitation of Symmetric Encryption
- Any exposure to the secret key compromises confidentiality of cipher.
- A key needs to be delivered to the recipient of the coded message for it to be deciphered
- Some intruders can get the key and BOOM! No secret anymore.


#### Exercise
1. Change"Pass1233" text to Caesar Cipher
   Sdvv4566
3. What is the encoding method of "Rexler"
     Rot12
4. Change "Hello There" to cipher with a key to alphabet shift of "HACK"
     
### Asymmetric Encryption

- Uses a pair of key for encryption
      - public key for encryption
      - private key for decryption
![[Pasted image 20240904210626.png]] 


#### Types of asymmetric enc.
- Two most popular algorithms are RSA, & El Gamal
- RSA
   -

Tools
- there are lots of encoding/ encryption

![[Pasted image 20240904211748.png]]

##### wordlists
- are normal text file that contains Different Words that can be used to match hashes, or for checking some parameters repeatedly using some loops.
##### Custom Wordlists
- we can create our own Wordlist, We can Create text file and add our highly usable words .


### Python for cryptography

- We can use programming to do tools that can do our own encryption and encoding hash type
- There are so many methods, even you can do the encoding/decoding for the base64.
- You just need to understand the math's.
    






