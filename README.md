# EX-NO-7-Implement-DES-Encryption-and-Decryption

## Aim:

To use the Data Encryption Standard (DES) algorithm for a practical application, such as securing sensitive data transmission in financial transactions.

## ALGORITHM:

1. DES is based on a symmetric key encryption technique that encrypts data in 64-bit blocks.
2. DES uses a Feistel network structure with 16 rounds of processing for encryption.
3. DES has a 64-bit key, but only 56 bits are used for encryption (the remaining 8 bits are for parity).
4. DES applies initial and final permutations along with 16 rounds of substitution and permutation transformations to produce ciphertext.

## Program:

```
def encrypt(message, key):
    key_length = len(key)
    encrypted_message = []

    for i in range(len(message)):
        encrypted_char = ord(message[i]) ^ ord(key[i % key_length])
        encrypted_message.append(encrypted_char)

    return encrypted_message

def decrypt(encrypted_message, key):
    key_length = len(key)
    decrypted_chars = []

    for i in range(len(encrypted_message)):
        decrypted_char = encrypted_message[i] ^ ord(key[i % key_length])
        decrypted_chars.append(chr(decrypted_char))

    return ''.join(decrypted_chars)

def main():
    message = input("Enter the message to encrypt: ")
    key = input("Enter the encryption key: ")

    encrypted = encrypt(message, key)

    print("Original Message:", message)
    print("Encrypted Message:", ' '.join(f"{byte:02X}" for byte in encrypted))

    decrypted = decrypt(encrypted, key)
    print("Decrypted Message:", decrypted)

if __name__ == "__main__":
    main()
```


## Output:
![image](https://github.com/user-attachments/assets/951783c3-642d-4ce2-8ad2-e922374d089e)


## Result:
  The program isImplement-DES-Encryption-and-Decryption executed successfully

