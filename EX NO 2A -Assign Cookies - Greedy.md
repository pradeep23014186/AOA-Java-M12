
# EX 2A Assign Cookies using Greedy Algorithm. 
## DATE: 20/04/2026
## AIM:
To Write a Java program for the following Constraints.
Assume you are an awesome parent and want to give your children some cookies. But, you should give each child at most one cookie.

Each child i has a greed factor g[i], which is the minimum size of a cookie that the child will be content with; and each cookie j has a size s[j]. If s[j] >= g[i], we can assign the cookie j to the child i, and the child i will be content. Your goal is to maximise the number of your content children and output the maximum number.

## Algorithm
1. Start the program and read the greed factors of children and cookie sizes.
2. Sort both the greed array and cookie size array in ascending order.
3. Initialize two pointers to traverse the children and cookies arrays.
4. Compare the current cookie size with the current child’s greed factor. If the cookie satisfies the child, move to the next child; otherwise, check the next cookie.
5. Count the number of satisfied children, print the result, and stop the program.   

## Program:
```
Program to implement Reverse a String
Developed by: Krishna Prasad S
Register Number: 212223230108
```
```java
import java.util.*;

public class AssignCookies 
{
    public static int findContentChildren(int[] g, int[] s) 
    {
        Arrays.sort(g);
        Arrays.sort(s);
        int i = 0, j = 0;
        while(i < g.length && j < s.length)
        {
            if(s[j] >= g[i])
            {
                i++;
            }
            else
            {
                j++;
            }
        }
        return i;
    }

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int n = sc.nextInt();
        int[] g = new int[n];
        for (int i = 0; i < n; i++) g[i] = sc.nextInt();
        int m = sc.nextInt();
        int[] s = new int[m];
        for (int i = 0; i < m; i++) s[i] = sc.nextInt();
        System.out.println(findContentChildren(g, s));
    }
}

```

## Output:

<img width="342" height="344" alt="output1" src="https://github.com/user-attachments/assets/8cac1079-2cbe-4f58-ab49-d98c08af423d" />


## Result:
The program successfully print all the numbers from 1 to N. 
