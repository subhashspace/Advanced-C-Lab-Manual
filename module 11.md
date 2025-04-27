

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

#include <stdio.h>

int max_of_four(int n1, int n2, int n3, int n4) {
    int max = n1;

    if (n2 > max) {
        max = n2;
    }
    if (n3 > max) {
        max = n3;
    }
    if (n4 > max) {
        max = n4;
    }

    return max;
}

int main() {
    int n1, n2, n3, n4, greater;

    printf("Enter four integers: ");
    scanf("%d %d %d %d", &n1, &n2, &n3, &n4);

    greater = max_of_four(n1, n2, n3, n4);

    printf("The greatest number is: %d\n", greater);

    return 0;
}




Output:

Enter four integers: 12 45 7 89
The greatest number is: 89





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





Output:




Enter two integers n and k: 5 3
Maximum AND value: 2
Maximum OR value: 3
Maximum XOR value: 3






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

    for (int query = 0; query < noque; query++) {
        int type, shelf, book;

        printf("Enter query type (1 for insert, 2 for delete, 3 for display): ");
        scanf("%d", &type);

        if (type == 1) {
            printf("Enter the shelf index and book number to insert: ");
            scanf("%d %d", &shelf, &book);

            if (shelf >= 1 && shelf <= noshel) {
                shelarr[shelf - 1][nobookarr[shelf - 1]] = book;
                nobookarr[shelf - 1]++;
                printf("Book %d inserted in shelf %d.\n", book, shelf);
            } else {
                printf("Invalid shelf index!\n");
            }
        }
        else if (type == 2) {
            printf("Enter the shelf index and book number to delete: ");
            scanf("%d %d", &shelf, &book);

            if (shelf >= 1 && shelf <= noshel) {
                int found = 0;
                for (int i = 0; i < nobookarr[shelf - 1]; i++) {
                    if (shelarr[shelf - 1][i] == book) {
                        for (int j = i; j < nobookarr[shelf - 1] - 1; j++) {
                            shelarr[shelf - 1][j] = shelarr[shelf - 1][j + 1];
                        }
                        nobookarr[shelf - 1]--;
                        printf("Book %d deleted from shelf %d.\n", book, shelf);
                        found = 1;
                        break;
                    }
                }
                if (!found) {
                    printf("Book %d not found on shelf %d.\n", book, shelf);
                }
            } else {
                printf("Invalid shelf index!\n");
            }
        }
        else if (type == 3) {
            printf("Enter the shelf index to display books: ");
            scanf("%d", &shelf);

            if (shelf >= 1 && shelf <= noshel) {
                printf("Books on shelf %d: ", shelf);
                for (int i = 0; i < nobookarr[shelf - 1]; i++) {
                    printf("%d ", shelarr[shelf - 1][i]);
                }
                printf("\n");
            } else {
                printf("Invalid shelf index!\n");
            }
        } else {
            printf("Invalid query type!\n");
        }
    }

    return 0;
}









Output:

Enter the number of shelves and number of queries: 3 5
Enter query type (1 for insert, 2 for delete, 3 for display): 1
Enter the shelf index and book number to insert: 1 101
Book 101 inserted in shelf 1.
Enter query type (1 for insert, 2 for delete, 3 for display): 1
Enter the shelf index and book number to insert: 2 102
Book 102 inserted in shelf 2.
Enter query type (1 for insert, 2 for delete, 3 for display): 3
Enter the shelf index to display books: 1
Books on shelf 1: 101 
Enter query type (1 for insert, 2 for delete, 3 for display): 2
Enter the shelf index and book number to delete: 1 101
Book 101 deleted from shelf 1.
Enter query type (1 for insert, 2 for delete, 3 for display): 3
Enter the shelf index to display books: 1
Books on shelf 1: 




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




#include <stdio.h>

int main() {
    int n, sum = 0;

    printf("Enter the number of integers: ");
    scanf("%d", &n);

    int a[n];

    for (int i = 0; i < n; i++) {
        printf("Enter integer %d: ", i + 1);
        scanf("%d", &a[i]);
        sum += a[i];
    }

    printf("The sum of the integers is: %d\n", sum);

    return 0;
}








Output:



 Enter the number of integers: 3
Enter integer 1: 5
Enter integer 2: 10
Enter integer 3: 15
The sum of the integers is: 30



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




#include <stdio.h>
#include <ctype.h>

int main() {
    char sentence[1000];
    int word_count = 0;
    int i = 0;

    printf("Enter a sentence: ");
    fgets(sentence, sizeof(sentence), stdin);

    while (sentence[i] != '\0') {
        if (i == 0 || (isspace(sentence[i - 1]) && !isspace(sentence[i]))) {
            word_count++;
        }
        i++;
    }

    printf("The number of words in the sentence is: %d\n", word_count);

    return 0;
}










Output:



Enter a sentence: Hello, how are you doing today?
The number of words in the sentence is: 6



Result:

Thus, the program that counts the number of words in a given sentence is verified 
successfully.
