# Shors Algorithm
In this repositroy, I want to take the oppertunity to describe Shor's algorithm, and the basics for how it works. This is a brief overview of the algorithm. 

There is some code in this repository and the code is based on the paper called, "Circuit for Shor’s algorithm using 2n+3 qubits".

This is not my code. I was not able to write all the code for the algorithm by myself... it was too complicated. The code in this repository was the code I used to replicate Shor's algorithm on my jupyter notebook and I am sharing it so you can try it too!

# Problem
RSA encryption is a method of encrypting messages provided two unique values for N and e. This encryption works by creating a 1-way function where encrypting is easy while decrypting becomes almost imposible. The securtiy is based on the exponentially hard problem called factorization which takes advantage of bit-based computational capabilities.

By the way, this is a short description of the logic behind it which you can also check out in a [video](https://www.youtube.com/watch?v=zqS4w4SiJT0) I made. Check it out!

## Preface
As a preface, I can start by defining a bunch of variables:

**N** = Public RSA encryptor

**e** = Public RSA exponent

**p** = RSA encryptor prime factor

**q** = RSA encryptor prime factor

**a** = Co-prime number to N, base for the exponent for Shor's function

**r** = Period of Shor's function function

**m** = Sending message

**c** = Encrypted message

There are more but in trying to make this as easy to understand as possible, these variables are enough.

### Public key
This is the key that is given to everyone, the values of both N and e. Anyone that wants to send a message is given these two pieces of information to encode m into c.

The formula to encrypt a message is given by:

c = m<sup>e</sup> mod(N)

## Step 1
