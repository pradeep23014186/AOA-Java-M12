
# EX 2B Jump Game using Greedy Algorithm.
## DATE: 20/204/2026
## AIM:
To write a Java program to for given constraints.
You are given an array of integers. Each number represents the maximum number of steps you can jump forward from that position.

You start from the first element (index 0). 
Write a program to find the minimum number of jumps required to reach the last index of the array.

If it is not possible to reach the end, return -1.
## Algorithm
1. Start the program and read the size and elements of the array.
2. Initialize a variable maxreach to store the farthest index that can be reached.
3. Traverse the array from the first element to the last.
4. If the current index is greater than maxreach, return false because the end cannot be reached; otherwise, update maxreach with the maximum reachable position.
5. If the loop completes successfully, return true indicating the last index can be reached, then stop the program.  

## Program:
```
Program to implement Reverse a String
Developed by: Krishna Prasad S
Register Number: 212223230108
```
```java
import java.util.Scanner;

public class JumpGame {

    // Function to check if we can reach the last index
    public static boolean canReachLastIndex(int[] nums) 
    {
        int maxreach = 0;
        for(int i=0; i<nums.length; i++)
        {
            if(i > maxreach)
            {
                return false;
            }
            maxreach = Math.max(maxreach, i + nums[i]);
        }
        return true;
    }

    // Main method for input and calling the function
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int n = sc.nextInt(); // Size of array
        int[] nums = new int[n];
        for (int i = 0; i < n; i++) {
            nums[i] = sc.nextInt(); // Elements of array
        }

        System.out.println("Can reach last index: " + canReachLastIndex(nums));
    }
}
```

## Output:

<img width="753" height="248" alt="output2" src="https://github.com/user-attachments/assets/dcbc1a09-e6dc-45e5-a49e-76fc484171b4" />


## Result:
The program successfully implemented and the expected output is verified.
