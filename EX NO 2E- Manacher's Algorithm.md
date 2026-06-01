
# EX 2E Pattern Matching using KMP Algorithm.
## DATE: 24/04/2026
## AIM:
To write a Java program for the following constraints.
Longest Palindromic Substring
Given a string s, return the longest palindromic substring in s.
using Manacher's Algorithm

## Algorithm
1. Start the program and read the input string from the user.
2. Transform the string by inserting special characters between each character to handle even and odd length palindromes uniformly.
3. Traverse the transformed string and expand around each character to calculate the palindrome length using Manacher’s Algorithm.
4. Keep track of the center and maximum length of the longest palindrome found during traversal.
5. Extract the longest palindromic substring from the original string, print the result, and stop the program.  

## Program:
```
Program to implement Reverse a String
Developed by: Krishna Prasad S
Register Number: 212223230108
```
```java
import java.util.Scanner;

public class Solution {
    
    public String longestPalindrome(String s) {
        if (s == null || s.length() == 0) return "";
        StringBuilder sb = new StringBuilder("^");
        for (char c : s.toCharArray()) 
        {
            sb.append("#").append(c);
        }
        sb.append("#$");

        String t = sb.toString();
        int n = t.length();
        int[] p = new int[n];
        int center = 0, right = 0;
        int maxLen = 0, centerIndex = 0;
        for (int i = 1; i < n - 1; i++) 
        {
            int mirror = 2 * center - i;
            if (i < right) 
            {
                p[i] = Math.min(right - i, p[mirror]);
            }
            while (t.charAt(i + (1 + p[i])) == t.charAt(i - (1 + p[i]))) 
            {
                p[i]++;
            }
            if (i + p[i] > right) 
            {
                center = i;
                right = i + p[i];
            }
            if (p[i] > maxLen) 
            {
                maxLen = p[i];
                centerIndex = i;
            }
        }
        int start = (centerIndex - maxLen) / 2;
        return s.substring(start, start + maxLen);
    }

    // Main method for user input
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        //System.out.println("Enter a string:");
        String input = scanner.nextLine();

        Solution sol = new Solution();
        String result = sol.longestPalindrome(input);

        System.out.println("Longest Palindromic Substring: " + result);
        scanner.close();
    }
}

```

## Output:

<img width="840" height="196" alt="output5" src="https://github.com/user-attachments/assets/c2a40de9-93e5-4c18-98a2-8a15c2e761ed" />


## Result:
The program successfully implemented and the expected output is verified.
