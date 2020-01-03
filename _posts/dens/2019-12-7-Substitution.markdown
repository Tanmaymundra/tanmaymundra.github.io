---
layout: post
title:  "Substitution/Caesar Cipher!"
date:   2019-12-7 15:12:54 +0530
categories: dens
permalink: article/:title
author: Tanmay Mundra
tags: [dens,ciphertext,substitution]
image: https://images.unsplash.com/photo-1513789181297-6f2ec112c0bc?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&w=1000&q=80
share-image: https://images.unsplash.com/photo-1513789181297-6f2ec112c0bc?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&w=1000&q=80
---

Cryptography involves communication between two users through coded message. Cryptography is an art and science of concealing the information to introduce privacy and secrecy between the intended users. The three basic goals of security are Confidentiality, Integrity and Availability.
Cryptography involves three basic mechanisms 
  * Symmetric-Key Encipherment or Private Key 
  * Asymmetric-Key Encipherment or Public Key
  * Hashing

### Symmetric key encipherment 

A single secret key is used for both encryption and decryption. In addition, the encryption and decryption algorithms are inverses of each other. The original message known as plain text is encrypted using a secret key to obtain the unintelligible message called cipher text. This cipher text is transmitted through the channel to the intended receiver. At the receiver, the cipher text is decrypted using the same secret key to obtain the original plain text.Traditional Symmetric Ciphers are the foundation to modern ciphers which are classified into two broad categories
 * **Substitution Cipher**
    
    A substitution cipher replaces one symbol with another stored in the Character list along with index. 
 
 * **Transposition Cipher**
 
    A transposition cipher does not substitute one symbol for another, instead it changes or transposes the location of the symbols.  

### Implementation of Substitution/Caesar Cipher
   
####  Algorithm

   * Enter the default Character List
      
      ```python
      import string
      all_letters= string.ascii_letters
      digits="0123456789"
      all_char=all_letters+digits
      print('Character List :', all_char)

      #>Character List: abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ0123456789 
      ```

   * Enter the plain text and key

      ```python
      x = input('Enter The String to be Encrypted :')
      k = int(input('Enter the key value :'))

      #=> Enter The String to be Encrypted : Hello from the other Side
      #=> Enter the key value : 6
      ```

   * Obtain cipher text as follows. 

     > C= (P+K) mod n where 
     > 
     > - C -> Ciphered Character
     > - P -> Plain Text Character
     > - K -> Key
     > - n -> Length of the character list

      ```python
      word=''
      for letter in x:
        if (letter in all_char):
          z= all_char.find(letter)
          y=all_char[(z+k)%len(all_char)]
          word+=y
        else:
          word+= letter

      print('Plain Text : ', x)
      print('Encrypted Data : ', word)
      print('Key Value : ',k)

      #=> Plain Text : Hello from the other Side
      #=> Encrypted Data : Nkrru lxus znk uznkx Yojk
      #=> Key Value :  6
      ```

   * Obtain deciphered text by reversing the logic.
      ```python
      word2=''
      for letter in word:
        if (letter in all_char):
          u= all_char.find(letter)
          v=all_char[(u-k)%len(all_char)]
          word2+=v
        else:
          word2+= letter
      
      print('Encrypted Data : ', word)
      print('Plain Text : ', word2)
      print('Key Value : ',k)
      
      #=> Encrypted Data : ZgtsgE-98
      #=> Plain Text : Tanmay-32
      #=> Key Value : 6
      ```
   
### Transposition Cipher and Reverse Cipher
    
####  Algoritm

  * Enter the plain text and the positions by which the text has to be transposed

    ```python
    x1 = input('Enter The String to be Encrypted :')
    k1= int(input('Enter the key value :'))

    #=> Enter The String to be Encrypted : Tanmay
    #=> Enter the key value : 3
    ```

  * Apply the circular shift logic to obtain the Transposition Cipher

    ```python
    word3=''

    for index,char in enumerate(x1):
      v1=x1[((index + k1)% len(x1))]
      word3 +=v1

    print('')
    print('Encrypted Data : ', word3)
    print('Plain Text : ', x1)
    print('Key Value : ',k1)

    #=> Encrypted Data :  mayTan
    #=> Plain Text :  Tanmay
    #=> Key Value :  3
    ```  
  * Apply reverse logic to obtain the plain text back

Python Code hosted on [Google Collab](https://colab.research.google.com/drive/1VQ8B-Z1AaSX3T1UcIbCfurLwikRKC54j) 
