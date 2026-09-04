# EX-NO14-HASH-ALGORITHM
## NAME: SHALINI N
## REG NO: 212224040305

## AIM:
To implement HASH ALGORITHM

## ALGORITHM:

1. Hash Algorithm is used to convert input data (message) into a fixed-size string, typically a hash value, which uniquely represents the original data.

2. Initialization:
   - Choose a hash function \( H \) (e.g., SHA-256, MD5, etc.).
   - The message \( M \) to be hashed is input.

3. Message Preprocessing:
   - Break the message \( M \) into fixed-size blocks. If necessary, pad the message to make it compatible with the block size required by the hash function.
   - For example, in SHA-256, the message is padded to ensure that its length is a multiple of 512 bits.

4. Hash Calculation:
   - Process the message block by block, applying the hash function \( H \) iteratively to produce an intermediate hash value.
   - For SHA-256, each block is processed through a series of logical operations, bitwise manipulations, and modular additions.

5. Output:
   - After all blocks are processed, the final hash value (digest) is produced, which is a fixed-size output (e.g., 256-bit for SHA-256).
   - The resulting hash is unique to the input message, meaning even a small change in the message will result in a completely different hash.

6. Security: The strength of the hash algorithm lies in its collision resistance, ensuring that it is computationally infeasible to find two different messages that produce the same hash value.


## Program:
```
#include <stdio.h>
#include <string.h>

# Hash Function
# This function converts the given message
# into a fixed hash value.
unsigned long hashFunction(char *str)
{
    unsigned long hash = 5381;
    int c;

    # Read each character of the message
    # and calculate the hash value.
    while ((c = *str++))
    {
        hash = ((hash << 5) + hash) + c;
    }

    # Return the calculated hash value.
    return hash;
}

# Main Function
int main()
{
    char message[100];
    unsigned long hash;

    # Get the message from the user.
    printf("Enter the message: ");
    fgets(message, sizeof(message), stdin);

    # Remove the newline character
    # added by fgets().
    message[strcspn(message, "\n")] = '\0';

    # Call the hash function
    # to calculate the hash value.
    hash = hashFunction(message);

    # Display the generated hash value.
    printf("Hash Value: %lu\n", hash);

    return 0;
}
```

## Output:

<img width="1522" height="595" alt="image" src="https://github.com/user-attachments/assets/781d3e9f-39d4-4069-9a2d-cc2b60511b3b" />

## Result:
The program is executed successfully.
