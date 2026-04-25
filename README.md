## EX. NO: 1 : IMPLEMENTATION OF CAESAR CIPHER
 

## AIM:

To implement the simple substitution technique named Caesar cipher using C language.

## DESCRIPTION:

To encrypt a message with a Caesar cipher, each letter in the message is changed using a simple rule: shift by three. Each letter is replaced by the letter three letters ahead in the alphabet. A becomes D, B becomes E, and so on. For the last letters, we can think of the
alphabet as a circle and "wrap around". W becomes Z, X becomes A, Y bec mes B, and Z
becomes C. To change a message back, each letter is replaced by the one three before it.

## EXAMPLE:



![image](https://github.com/Hemamanigandan/CNS/assets/149653568/eb9c6c43-8c80-4cdd-b9d4-91705a311c79)


## ALGORITHM:

### STEP-1: Read the plain text from the user.
### STEP-2: Read the key value from the user.
### STEP-3: If the key is positive then encrypt the text by adding the key with each character in the plain text.
### STEP-4: Else subtract the key from the plain text.
### STEP-5: Display the cipher text obtained above.


## PROGRAM :-
```c

#include <stdio.h>
#include <ctype.h>
#include <string.h>

void encrypt(char text[], int key, char cipher[]) {
    int i;
    for (i = 0; text[i] != '\0'; i++) {
        if (isupper(text[i]))
            cipher[i] = ((text[i] - 'A' + key) % 26) + 'A';
        else if (islower(text[i]))
            cipher[i] = ((text[i] - 'a' + key) % 26) + 'a';
        else
            cipher[i] = text[i];
    }
    cipher[i] = '\0';
}

void decrypt(char cipher[], int key, char plain[]) {
    int i;
    for (i = 0; cipher[i] != '\0'; i++) {
        if (isupper(cipher[i]))
            plain[i] = ((cipher[i] - 'A' - key) % 26 + 26) % 26 + 'A';
        else if (islower(cipher[i]))
            plain[i] = ((cipher[i] - 'a' - key) % 26 + 26) % 26 + 'a';
        else
            plain[i] = cipher[i];
    }
    plain[i] = '\0';
}

int main() {
    char plain[100], cipher[100], decrypted[100];
    int key;

    printf("Enter the plain text: ");
    fgets(plain, sizeof(plain), stdin);
    plain[strcspn(plain, "\n")] = 0;

    printf("Enter the key value: ");
    scanf("%d", &key);

    printf("\nPLAIN TEXT: %s\n", plain);

    encrypt(plain, key, cipher);
    printf("ENCRYPTED TEXT: %s\n", cipher);

    decrypt(cipher, key, decrypted);
    printf("DECRYPTED TEXT: %s\n", decrypted);

    return 0;
}

```


## OUTPUT :-



<img width="1849" height="998" alt="image" src="https://github.com/user-attachments/assets/6c858bea-ffd1-4338-8071-18c77911681c" />




## Result:
The implementation of the simple substitution technique named Caesar cipher using C language was completed and executed successfully.

