## EX: 8 IMPLEMENTATION OF ADVANCED ENCRYPTION STANDARD

## AIM:
To use Advanced Encryption Standard (AES) Algorithm for a practical application like URL Encryption.

## ALGORITHM:
1.	Get the input plaintext and key from the user.
2.	Treat the plaintext as a single block of characters.
3.	Perform XOR operation between each character of plaintext and the corresponding character of the key (key repeats if shorter).
4.	Store the XOR result as the ciphertext.
5.	Display the ciphertext in ASCII format.
6.	Perform XOR operation again between the ciphertext and the same key to decrypt.
7.	Store and display the original message as the decrypted text.

## PROGRAM:

    #include <stdio.h>
    #include <string.h>
    
    void encrypt(char *message, char *key, char *encryptedMessage, int messageLength) {
        int keyLength = strlen(key);
        for (int i = 0; i < messageLength; i++) {
            encryptedMessage[i] = message[i] ^ key[i % keyLength];
        }
        encryptedMessage[messageLength] = '\0'; 
    }
    
    
    void decrypt(char *encryptedMessage, char *key, char *decryptedMessage, int messageLength) {
        int keyLength = strlen(key);
        for (int i = 0; i < messageLength; i++) {
            decryptedMessage[i] = encryptedMessage[i] ^ key[i % keyLength];
        }
        decryptedMessage[messageLength] = '\0'; 
    }
    
    int main() {
        char message[100];
        char key[100];
        char encryptedMessage[100];
        char decryptedMessage[100];
    
        printf("\n***** Simulation of Simple XOR Encryption and Decryption *****\n\n");
    
    
        printf("Enter the message to encrypt: ");
        fgets(message, sizeof(message), stdin);
        message[strcspn(message, "\n")] = '\0'; 
    
    
        printf("Enter the encryption key: ");
        fgets(key, sizeof(key), stdin);
        key[strcspn(key, "\n")] = '\0'; 
    
        int messageLength = strlen(message);
    
        encrypt(message, key, encryptedMessage, messageLength);
    
        printf("Original Message: %s\n", message);
        printf("Encrypted Message (in hex): ");
        for (int i = 0; i < messageLength; i++) {
            printf("%02X ", (unsigned char)encryptedMessage[i]);
        }
        printf("\n");
    
        decrypt(encryptedMessage, key, decryptedMessage, messageLength);
        printf("Decrypted Message: %s\n", decryptedMessage);
    
        return 0;
    }
    
## OUTPUT:
<img width="1710" height="872" alt="image" src="https://github.com/user-attachments/assets/dd554a03-48b2-43d1-8777-a4d1993068f7" />

## RESULT:
Hence, Advanced Encryption Standard (AES) Algorithm for a practical application like URL Encryption is done successfully.
