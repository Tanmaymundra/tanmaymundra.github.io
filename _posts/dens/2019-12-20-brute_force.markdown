---
layout: post
title:  "Cryptanalysis on Traditional Cipher"
date:   2019-12-20
categories: jekyll cat
permalink: article/:title
author: Tanmay Mundra
---

Cryptography is the science and art of creating secret codes, whereas cryptanalysis is the science and art of breaking those codes. We need to learn cryptanalysis techniques to understand the vulnerability of our cryptosystem and enables us to strengthen it. 

The common cryptanalysis attacks are
* Ciphertext-only
* Known-plaintext
* Chosen-plaintext
* Chosen-ciphertext.

### Ciphertext-only attack

The attacker has access to only some cipher text. The attacker tries to find the corresponding key and plain text. The assumption is that the attacker knows the algorithm and can intercept the cipher text.

The various methods used for ciphertext-only attack are
* Brute-Force Attack
* Statistical Attack
* Pattern Attack.

In  `Brute-Force` Attack or exhaustive-key-search method, the attacker tries to use all the possible keys. We assume that the algorithm and the key domain (the list of all possible keys) are known to the attacker. Using the intercepted cipher, the attacker decrypts the cipher text with every possible key until the plain text makes sense. To prevent this attack, the number of possible keys must be very large. 

### 	Caesar Cipher Encryption 

#### 	Algorithm


* Enter the plain text - P
* Enter the key
* Enter modulus or length of character list ( n ). 
* Obtain cipher text as follows.  C= (P+K)mod n

### Reverse Cipher

#### Algoritm

* Enter the plain text
* Enter the positions(key) by which the text has to be transposed
* Apply the circular shift logic to obtain the Transposition Cipher.

[Read More](substitution)

### Brute Force Attack on Caesar Cipher

#### Algorithm

* Enter the cipher text C

```python
import string
all_letters= string.ascii_letters
digits="0123456789"
all_char=all_letters+digits
print('Character List :', all_char)
enc_data= input('Enter the text to be decoded : ')

#=> Character List : abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ0123456789
#=> Enter the text to be decoded : YnotE LuD
``` 
* Obtain deciphered text as follows for all the possible values of the key K

```python
for k in range(len(all_char)):
  word=''
  for letter in enc_data:
    if (letter in all_char):
      z= all_char.find(letter)
      y=all_char[(z-k)%len(all_char)]
      word+=y
    else:
      word+= letter
print('Key Value:',k,'-',' Decrypted Text: ',word )
```

```
__Brute Force Attack Output__

Key Value: 0 -  Decrypted Text:  YnotE LuD
Key Value: 1 -  Decrypted Text:  XmnsD KtC
Key Value: 2 -  Decrypted Text:  WlmrC JsB
Key Value: 3 -  Decrypted Text:  VklqB IrA
Key Value: 4 -  Decrypted Text:  UjkpA Hqz
Key Value: 5 -  Decrypted Text:  Tijoz Gpy
Key Value: 6 -  Decrypted Text:  Shiny Fox #<===
Key Value: 7 -  Decrypted Text:  Rghmx Enw
Key Value: 8 -  Decrypted Text:  Qfglw Dmv
.
.
Key Value: 60 -  Decrypted Text:  0pqvG NwF
Key Value: 61 -  Decrypted Text:  ZopuF MvE
```
* DC= (C-K)mod n

The key corresponding to the intelligible deciphered text would be the key used to encrypt the plain text. 



### Brute Force Attack on Reverse Cipher

#### Algoritm

* Enter the cipher text C

```python
x1 = input('Enter The String to be Decrypted :')

#=>Enter The String to be Encrypted :mayTan
``` 

* Apply the circular shift logic for all the different keys in the key domain. 

```python
for k in range(len(x1)):
  word2=''
  for index,char in enumerate(x1):
    v1=x1[((index - k)% len(x1))]
    word2 +=v1
  print('Key Value:',k,'-','Decrypted Data : ', word2)
```

``` 
Output

Key Value: 0 Decrypted Data :  mayTan
Key Value: 1 Decrypted Data :  nmayTa
Key Value: 2 Decrypted Data :  anmayT
**Key Value: 3 Decrypted Data :  Tanmay**
Key Value: 4 Decrypted Data :  yTanma
Key Value: 5 Decrypted Data :  ayTanm
```

* The key corresponding to the intelligible deciphered text would be the key used to encrypt the plain text. 

	`In this case the key is 3`


Python Code hosted on [Google Collab](https://colab.research.google.com/drive/1c5T1nPbo6FPxzqTkmoO06Qu_LVx5ukmx)