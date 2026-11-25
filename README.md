# EX-NO-9-RSA-Algorithm

### Name: M.Vetrivel
### Register Number: 212225040487
### Date: 25-11-2026

## AIM:
To Implement RSA Encryption Algorithm in Cryptography

## Algorithm:


Step 1: Design of RSA Algorithm  
The RSA algorithm is based on the mathematical difficulty of factoring the product of two large prime numbers. It involves generating a public and private key pair, where the public key is used for encryption, and the private key is used for decryption.

Step 2: Implementation in Python or C 
This algorithm can be implemented in languages like Python or C by performing large integer calculations for key generation, encryption, and decryption, utilizing libraries for modular arithmetic if necessary.

Step 3: Algorithm Description  
1. Key Generation:
   - Select two large prime numbers \( p \) and \( q \).
   - Calculate \( n = p \times q \), which will be used as the modulus.
   - Compute the totient \( \phi(n) = (p - 1)(q - 1) \).
   - Choose a public exponent \( e \) such that \( e \) is coprime with \( \phi(n) \).
   - Compute the private key \( d \), which is the modular inverse of \( e \) mod \( \phi(n) \).

2. Encryption:
   - Convert the plaintext message \( M \) into a numerical form \( m \) (such that \( 0 \le m < n \)).
   - Compute the ciphertext \( c \) using the formula: \( c = m^e \mod n \).

3. Decryption:
   - Use the private key \( d \) to recover \( m \) from \( c \) using: \( m = c^d \mod n \).
   - Convert \( m \) back into the original message \( M \).

Step 4: Mathematical Representation  
- Encryption: \( E(m) = m^e \mod n \)
- Decryption: \( D(c) = c^d \mod n \)

Step 5: **Security Foundation  
The security of RSA relies on the difficulty of factoring large numbers; thus, choosing sufficiently large prime numbers for \( p \) and \( q \) is crucial for security.

## Program:
```C
#include <stdio.h>

int main()
{
    int p = 3, q = 11;
    int n, phi, e = 3, d = 7;
    int msg, encrypted, decrypted;

    n = p * q;
    phi = (p - 1) * (q - 1);

    printf("Enter a message (number): ");
    scanf("%d", &msg);

    encrypted = 1;
    for (int i = 0; i < e; i++)
        encrypted = (encrypted * msg) % n;

    decrypted = 1;
    for (int i = 0; i < d; i++)
        decrypted = (decrypted * encrypted) % n;

    printf("Public Key: (%d, %d)\n", e, n);
    printf("Private Key: (%d, %d)\n", d, n);
    printf("Encrypted message: %d\n", encrypted);
    printf("Decrypted message: %d\n", decrypted);

    return 0;
}
```



## Output:
<img width="741" height="201" alt="Screenshot 2026-11-25 143138" src="https://github.com/user-attachments/assets/53d8e9b5-b3c6-467a-8d2f-37cbca19d028" />




## Result:
 The program is executed successfully.
