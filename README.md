# Ex-1 IMPLEMENTATION-OF-SYMBOL-TABLE
# Register Number : 212224040182
# Date : 30-08-2025
# AIM :
## To write a C program to implement a symbol table.
# ALGORITHM
1.	Start the program.
2.	Get the input from the user with the terminating symbol ‘$’.
3.	Allocate memory for the variable by dynamic memory allocation function.
4.	If the next character of the symbol is an operator then only the memory is allocated.
5.	While reading, the input symbol and memory address are inserted into the symbol table.
6.	The steps are repeated till ‘$’ is reached.
7.	To reach a variable, enter the variable to be searched and the symbol table has been checked for the corresponding variable, the variable along with its address is displayed as a result.
8.	Stop the program. 
# PROGRAM
```
#include <stdio.h>
#include <ctype.h>
#include <string.h>
#include <stdlib.h>

#define MAX_EXPRESSION_SIZE 100

int main() {
	int i = 0, j = 0, x = 0, n, flag = 0;
	int k;
	char b[MAX_EXPRESSION_SIZE], d[15], c, srch;

	printf("Enter the Expression terminated by $: ");
	while ((c = getchar()) != '$' && i < MAX_EXPRESSION_SIZE - 1) {
		b[i++] = c;
	}
	b[i] = '\0';
	n = i - 1;

	printf("\nGiven Expression: %s\n", b);

	printf("\nSymbol Table\n");
	printf("Symbol\tType\t\tAddress\n");

	for (j = 0; j <= n; j++) {
		c = b[j];
		if (isalpha((unsigned char)c)) {
			int alreadyExists = 0;
			for (k = 0; k < x; k++) {
				if (d[k] == c) {
					alreadyExists = 1;
					break;
				}
			}

			if (!alreadyExists) {
				d[x] = c;
				printf("%c\tidentifier\t%p\n", c, (void*)&d[x]);
				x++;
			}
		}
	}

	// Clear input buffer
	while ((c = getchar()) != '\n' && c != EOF);

	printf("\nEnter the symbol to search: ");
	srch = getchar();

	for (i = 0; i < x; i++) {
		if (srch == d[i]) {
			printf("Symbol Found\n");
			flag = 1;
			break;
		}
	}
	if (flag == 0)
		printf("Symbol Not Found\n");

	return 0;
}
```
# OUTPUT
# Symbol Found

<img width="844" height="437" alt="Screenshot 2025-09-18 151926" src="https://github.com/user-attachments/assets/5aa80e90-d845-4140-ad74-209c5ffcd947" />




# Symbol Not Found

<img width="837" height="427" alt="Screenshot 2025-09-18 151946" src="https://github.com/user-attachments/assets/3c62f0de-3b25-403e-a007-cff28b8558e5" />



# RESULT
### The program to implement a symbol table is executed and the output is verified.
