
# EX 2D Pattern Matching using Naive Approach.
## DATE: 22/04/2026
## AIM:
To write a Java program to for given constraints.
Given text string with length n and a pattern with length m, the task is to prints all occurrences of pattern in text.
Note: You may assume that n > m.

Examples: 

Input:  text = "THIS IS A TEST TEXT", pattern = "TEST"
Output: Pattern found at index 10

Input:  text =  "AABAACAADAABAABA", pattern = "AABA"
Output: Pattern found at index 0, Pattern found at index 9, Pattern found at index 12
## Algorithm
1. Start the program and read the text string and pattern string from the user.
2. Find the lengths of the text and pattern.
3. Traverse the text from index 0 to n - m and compare the pattern with the current substring of the text character by character.
4. If all characters match, print the starting index where the pattern is found.
5. Repeat the process until the end of the text and stop the program. 

## Program:
```
Program to implement Reverse a String
Developed by: Krishna Prasad S
Register Number: 212223230108
```
```java
import java.util.Scanner;

public class NaivePatternSearch {
    public static void search(String text, String pattern)
    {
        int n = text.length();
        int m = pattern.length();
        for(int i=0; i<= n-m; i++)
        {
            int j;
            for(j=0; j<m; j++)
            {
                if(text.charAt(i+j) != pattern.charAt(j))
                {
                    break;
                }
            }
            if(j == m)
            {
                System.out.println("Pattern found at index " + i);
            }
        }
    }

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        // Taking input from the user
        //System.out.print("Enter the text: ");
        String text = scanner.nextLine();

        //System.out.print("Enter the pattern: ");
        String pattern = scanner.nextLine();

        // Search for pattern in the text
        search(text, pattern);

        scanner.close();
    }
}

```
## Output:

<img width="784" height="259" alt="output4" src="https://github.com/user-attachments/assets/8c542e49-8439-4610-9fca-cfa81e819e5f" />


## Result:
The program successfully implemented and the expected output is verified.
