#include <stdio.h>
#include <string.h>
#include <ctype.h>
int isValidIdentifier(const char *str) {
    if (*str == '\0')
        return 0;
    if (!isalpha(*str) && *str != '_')
        return 0;
    for (int i = 1; str[i] != '\0'; i++) {
        if (!isalnum(str[i]) && str[i] != '_')
            return 0;
    }
    return 1;
}

int main() {
    char identifier[100];
    printf("Enter an identifier: ");
    scanf("%s", identifier);
    if (isValidIdentifier(identifier))
        printf("%s is a valid identifier.\n", identifier);
    else
        printf("%s is not a valid identifier.\n", identifier);
    return 0;
}
