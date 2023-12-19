#include <stdio.h>
#include <string.h>

void generateAsciiArt(char input[]) {
    // Define ASCII art patterns for each character (customize as needed)
    char asciiPatterns[26][8][8] = {
        {
            "  A  ",
            " A A ",
            "AAAAA",
            "A   A",
            "A   A"
        },
        // Define patterns for other characters...
    };

    // Iterate through each character in the input
    for (int i = 0; i < strlen(input); i++) {
        char currentChar = toupper(input[i]);

        // Check if the character is an uppercase letter
        if (currentChar >= 'A' && currentChar <= 'Z') {
            int index = currentChar - 'A';

            // Print the ASCII art pattern for the current character
            for (int row = 0; row < 5; row++) {
                printf("%s\n", asciiPatterns[index][row]);
            }
        } else {
            // Print a placeholder for non-alphabetic characters
            printf("   ");
        }

        // Add spacing between characters
        printf("   ");
    }

    printf("\n");
}

int main() {
    char userInput[100];

    // Get user input
    printf("Enter text for ASCII art: ");
    scanf("%s", userInput);

    // Generate and print ASCII art
    generateAsciiArt(userInput);

    return 0;
}
