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

**a** = Co-prime number to N, base for the exponent for Shor's function (Random number less than N that shares only one other factor with N, 1)

**r** = Period of Shor's function function

**m** = Message

**c** = Encrypted message

There are more but in trying to make this as easy to understand as possible, these variables are enough.

### Public key
This is the key that is given to everyone, the values of both N and e. Anyone that wants to send a message is given these two pieces of information to encode m into c.

The formula to encrypt a message is given by:

c = m<sup>e</sup> mod(N)

This is the easy part of the one way function.

The hard part is going backwards to find m. 

The formula to decrypt a message is given by:

m = c<sup>d</sup> mod(N)

But, its not so simple, finding d requires to know both prime factors of N, p and q. And for a computer, this is alomst impossible to compute in a limited time period with current RSA numbers like the hundreds of digit numbers for N.

### Shor's Function
The general function formula is:

S(x) = a<sub>x</sub> mod(N)

When you sub in your own values for N and a it becomes:

f(x) = 2<sub>x</sub> mod(15)

### And Even More Prep

Lets define the public keys and go through the RSA framework once.

**N** = 15

**e** = 4

**m** = 11

c = 15<sup>4</sup> mod(15)

c = 1

This is the message your computer would craft and send to something like a bank to decode. Now lets figure out how to intercept this message with a quantum computer and find the message for ourselves.

## Step 1

