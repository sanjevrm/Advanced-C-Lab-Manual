

EXP NO:21 C PROGRAM TO CREATE A FUNCTION TO FIND THE GREATEST NUMBER
Aim:
To write a C program to create a function to find the greatest number

Algorithm:
1.	Include the necessary header #include <stdio.h>.
2.	Use a series of if and else if statements to compare the values and return the maximum among them.
3.	Declare variables n1, n2, n3, n4, and greater to store user input and the result.
4.	Use scanf to take four integers as input.
5.	Call the max_of_four function with the input integers and store the result in the greater variable
 
Program:
```
#include <stdio.h>
int max_of_four(int n1, int n2, int n3, int n4) {
    int greater = n1;

    if (n2 > greater)
        greater = n2;
    if (n3 > greater)
        greater = n3;
    if (n4 > greater)
        greater = n4;

    return greater;
}

int main() {
    int n1, n2, n3, n4, greater;
    printf("Enter four numbers: ");
    scanf("%d %d %d %d", &n1, &n2, &n3, &n4);
    greater = max_of_four(n1, n2, n3, n4);
    printf("The greatest number is: %d\n", greater);

    return 0;
}
```
Output:

![image](https://github.com/user-attachments/assets/79ed5bc7-acd5-4256-9a11-4b3297cd459b)


Result:
Thus, the program  that create a function to find the greatest number is verified successfully.


 
EXP NO:22 C PROGRAM TO PRINT THE MAXIMUM VALUES FOR THE AND, OR AND  XOR COMPARISONS
Aim:
To write a C program to print the maximum values for the AND, OR and XOR comparisons

Algorithm:
1.	Define a function calculate_the_max that takes two integers n and k as parameters.
2.	Declare variables a, o, and x to store the maximum values for AND, OR, and XOR operations, respectively.
3.	Use nested loops to iterate through pairs of integers (i, j) from 1 to n.
4.	Within the loops, check conditions for AND, OR, and XOR operations and update the corresponding maximum values (a, o, x).
5.	Declare variables n and k to store user input.
6.	Use scanf to take two integers as input.
7.	Call the calculate_the_max function with input values.
 
Program:
```
#include <stdio.h>
void calculate_the_max(int n, int k) {
    int a = 0, o = 0, x = 0;
    for (int i = 1; i <= n; i++) {
        for (int j = i + 1; j <= n; j++) {
            
            if ((i & j) > a && (i & j) < k) {
                a = i & j;
            }
           
            if ((i | j) > o && (i | j) < k) {
                o = i | j;
            }
            
            if ((i ^ j) > x && (i ^ j) < k) {
                x = i ^ j;
            }
        }
    }
    printf("Maximum AND value: %d\n", a);
    printf("Maximum OR value: %d\n", o);
    printf("Maximum XOR value: %d\n", x);
}

int main() {
    int n, k;
    printf("Enter two integers n and k: ");
    scanf("%d %d", &n, &k);
    calculate_the_max(n, k);

    return 0;
}
```
Output:

![image](https://github.com/user-attachments/assets/d1349bd2-dc17-4e26-b684-fedf60921a98)


Result:
Thus, the program to print the maximum values for the AND, OR and XOR comparisons
is verified successfully.


 
EXP NO:23 C PROGRAM TO WRITE THE LOGIC FOR THE REQUESTS
Aim:
To write a C program to write the logic for the requests

Algorithm:
1.	Declare variables noshel and noque to store the number of shelves and the number of queries, respectively.
2.	Use scanf to take two integers as input for the number of shelves and queries.
3.	Declare a 2D array shelarr to represent shelves and books, and an array nobookarr to store the number of books on each shelf.
4.	Declare variables k and c to keep track of the book index and the total number of books.
5.	Use a for loop to iterate over the queries.
 
Program:
```
#include <stdio.h>
int main() {
    int noshel, noque;
    printf("Enter the number of shelves and number of queries: ");
    scanf("%d %d", &noshel, &noque);
    
    int shelarr[noshel][100]; 
    int nobookarr[noshel];
    
   
    for (int i = 0; i < noshel; i++) {
        nobookarr[i] = 0; 
    }
    for (int q = 0; q < noque; q++) {
        int query_type;
        printf("\nEnter query type (1: Add books, 2: Display shelf books, 3: Exit): ");
        scanf("%d", &query_type);

        if (query_type == 1) {
           
            int shelf, num_books;
            printf("Enter shelf number (0 to %d) and number of books to add: ", noshel - 1);
            scanf("%d %d", &shelf, &num_books);
            
            if (shelf >= 0 && shelf < noshel) {
                for (int i = nobookarr[shelf]; i < nobookarr[shelf] + num_books; i++) {
                    shelarr[shelf][i] = i + 1; 
                }
                nobookarr[shelf] += num_books; 
                printf("%d books added to shelf %d.\n", num_books, shelf);
            } else {
                printf("Invalid shelf number.\n");
            }
        }
        
        else if (query_type == 2) {
            
            int shelf;
            printf("Enter shelf number (0 to %d) to display books: ", noshel - 1);
            scanf("%d", &shelf);
            
            if (shelf >= 0 && shelf < noshel) {
                if (nobookarr[shelf] > 0) {
                    printf("Books on shelf %d: ", shelf);
                    for (int i = 0; i < nobookarr[shelf]; i++) {
                        printf("%d ", shelarr[shelf][i]);
                    }
                    printf("\n");
                } else {
                    printf("No books on shelf %d.\n", shelf);
                }
            } else {
                printf("Invalid shelf number.\n");
            }
        }
        
        else if (query_type == 3) {
            printf("Exiting the program.\n");
            break;
        }
        
        else {
            printf("Invalid query type.\n");
        }
    }
    
    return 0;
}

```
Output:

![image](https://github.com/user-attachments/assets/9135a059-a318-4796-9c25-a56e7c80a2e5)



Result:
Thus, the program to write the logic for the requests is verified successfully.


 
EXP NO:24 C PROGRAM PRINT THE SUM OF THE INTEGERS IN THE ARRAY.
Aim:
To write a C program print the sum of the integers in the array.

Algorithm:
1.	Declare a variable n to store the number of integers.
2.	Use scanf to take an integer n as input.
3.	Declare an array a of size n to store the integers.
4.	Declare a variable sum and initialize it to zero.
5.	Use a for loop to iterate n times:
6.	Use scanf to input each integer and add it to the sum.
7.	Print the final sum using printf.



Program:
```
#include <stdio.h>
int main() {
    int n, sum = 0;
    printf("Enter the number of integers: ");
    scanf("%d", &n);
    int a[n];
    printf("Enter %d integers:\n", n);
    for (int i = 0; i < n; i++) {
        scanf("%d", &a[i]);
        sum += a[i];  
    }
printf("The sum of the integers is: %d\n", sum);
return 0;
}
```
Output:

![image](https://github.com/user-attachments/assets/72747c37-4597-49db-beb3-966325ed0963)


Result:
Thus, the program prints the sum of the integers in the array is verified successfully.


 
EXP NO 25: C PROGRAM TO COUNT THE NUMBER OF WORDS IN A      SENTENCE



Aim:

To write a C program that counts the number of words in a given sentence.

Algorithm:

1.	Input the sentence: Take a sentence from the user.
2.	Initialize a counter variable: This will keep track of the number of words.
3.	Process each character of the sentence:
o	Iterate through the sentence, checking each character.
o	If a character is not a space, it may belong to a word. If it's the first non-space character after a space or at the start, increment the word count.
4.	Handle spaces and punctuation: Skip over spaces, punctuation marks, and consider each word as a sequence of characters separated by spaces.
5.	Display the result: After processing the sentence, output the total word count.



Program:
```
#include <stdio.h>
#include <ctype.h>

int main() {
    char sentence[1000];
    int i, word_count = 0;
    int in_word = 0;
    printf("Enter a sentence: ");
    fgets(sentence, sizeof(sentence), stdin); 
    for (i = 0; sentence[i] != '\0'; i++) {
        
        if (isalnum(sentence[i])) {
            if (in_word == 0) {
                word_count++;
                in_word = 1; 
            }
        } else {
            in_word = 0;  }
    }
    printf("The number of words in the sentence is: %d\n", word_count);

    return 0;
}
```
Output:

![image](https://github.com/user-attachments/assets/e1f39e7a-0bd7-43f7-b04d-bad0eff12b76)

Result:

Thus, the program that counts the number of words in a given sentence is verified 
successfully.
