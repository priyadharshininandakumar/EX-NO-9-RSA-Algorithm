# EX-NO-9-RSA-Algorithm

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
```
#include <stdio.h>
int main()
{
    int p, q, n, phi, e, d;
    int m, c, i, j;
    printf("Enter two prime numbers: ");
    scanf("%d %d", &p, &q);
    n = p * q;
    phi = (p - 1) * (q - 1);
    for (e = 2; e < phi; e++)
    {
        int count = 0;
        for (i = 1; i <= e; i++)
        {
            if (e % i == 0 && phi % i == 0)
                count++;
        }
        if (count == 1)
            break;
    }
    for (d = 1; d < phi; d++)
    {
        if ((d * e) % phi == 1)
            break;
    }
    printf("Public Key: (%d, %d)\n", e, n);
    printf("Private Key: (%d, %d)\n", d, n);
    printf("Enter message (number): ");
    scanf("%d", &m);
    c = 1;
    for (i = 0; i < e; i++)
        c = (c * m) % n;
    printf("Encrypted message: %d\n", c);
    m = 1;
    for (i = 0; i < d; i++)
        m = (m * c) % n;
    printf("Decrypted message: %d\n", m);
    return 0;
}
```
## Output:
<img width="918" height="387" alt="image" src="https://github.com/user-attachments/assets/6284a915-f0dd-4170-a03b-5496bc90d728" />






## Result:


 The program is executed successfully.








 .





















 .































 .























 .























 .
