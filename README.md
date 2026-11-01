# EX-NO-7-Implement-DES-Encryption

## Aim:

To use the Data Encryption Standard (DES) algorithm for a practical application, such as securing sensitive data transmission in financial transactions.

## ALGORITHM:

1. DES is based on a symmetric key encryption technique that encrypts data in 64-bit blocks.
2. DES uses a Feistel network structure with 16 rounds of processing for encryption.
3. DES has a 64-bit key, but only 56 bits are used for encryption (the remaining 8 bits are for parity).
4. DES applies initial and final permutations along with 16 rounds of substitution and permutation transformations to produce ciphertext.

## Program:
This C program uses the OpenSSL DES library to perform encryption.
```
#include <stdio.h>
#include <string.h>
#include <openssl/des.h>

int main()
{
    DES_cblock key = "12345678";
    DES_key_schedule schedule;

    DES_cblock input = "HELLO123";
    DES_cblock output;

    DES_set_key_unchecked(&key, &schedule);

    DES_ecb_encrypt(&input, &output, &schedule, DES_ENCRYPT);

    printf("Original Text: %.8s\n", input);
    printf("Encrypted Text: ");

    for(int i = 0; i < 8; i++)
        printf("%02X", output[i]);

    printf("\n");

    return 0;
}
```

## Output:
```
Original Text: HELLO123
Encrypted Text: 96D0028878D58C89
```
## Result:
  The program is executed successfully

