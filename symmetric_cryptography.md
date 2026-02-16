DES - Data encryption standards 
    - designed in the 1970's by IBM for unclassified communication
    - uses the Feistel function 
    - not used anymore because it has been hacked in the past and isn't considered secure 
    - symmetric encryption algorithm 
    - block cipher operating on 64-bit blocks using a 56-bit key

 ### 2048 bit or higher is now considered secure

Triple DES - or 3 DES
  - feeds plain text into DES, AND GETS k1 (key 1)
      - then feeds that into DES again, getting k2, and again to k3 (cipher text)
  - much stronger than old style DES, BUT STILL BEING PHASED OUT NOW!
    - 112 bits

  ### DOUBLE DES is no more secure than standard DES, because of meet-in-the-middle attack!

AES (advanced encryption standard) - uses the Rijndael algorithm
  - uses a combination of substitution and transposition functions to achieve strong encryption
  - symmetric algorithm
  - block cipher operating on 128-bit blocks
  - key length of 128, 192, or 256 bits
      - all considered secure
   
Blowfish
  - public domain algorithm designed as a possible DES replacement
  - uses a feistel network that combines substitution and transposition operations 
  - symmetric algorithm
  - block cipher operating at 64-bit blocks
  - key length of any kind between 32 and 448 bits
      - no longer considered secure
   
Twofish
  - uses a feistel network
  - symmetric encryption algorithm
  - works on 128-bit blocks
  - uses key length of 128, 192, or 256 bits

  ### A small block size means patterns start repeating when encrypting large amounts of data (called a birthday attack problem).

Steganography - the process of hiding info within another file so that it is not visible to the naked eye 
  - hiding text within an image file (which has millions of individual pixels... easy to hide somewhere), video, or audio
     - makes slight modifications to image pixels (adjusting the shade of a pixel by 1 or 2 tones) to create a hiding place
          - you can't notice even if a few thousand were manipulated
       - OpenStego - program used for steganography (used to hide and extract data) from photo
           
