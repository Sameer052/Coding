# Coding
Repository
#include <stdio.h>

int isVowel(char ch) {
    return ch == 'A' || ch == 'E' || ch == 'I' || ch == 'O' || ch == 'U' || ch == 'Y';
}

int isEvenSum(char tag[]) {
    int i;
    for (i = 0; i < 8; i++) {
        if (tag[i] >= '0' && tag[i] <= '9' && tag[i+1] >= '0' && tag[i+1] <= '9') {
            int sum = (tag[i] - '0') + (tag[i+1] - '0');
            if (sum % 2 != 0) {
                return 0; // Return 0 for odd sum
            }
        }
    }
    return 1; // Return 1 for even sums
}

int isValidTag(char tag[]) {
    if (isVowel(tag[2])) {
        return 0; // Return 0 for invalid vowel
    }
    return isEvenSum(tag);
}

int main() {
    char tag[11];
    scanf("%s", tag);

    if (isValidTag(tag)) {
        printf("valid\n");
    } else {
        printf("invalid\n");
    }

    return 0;
}
