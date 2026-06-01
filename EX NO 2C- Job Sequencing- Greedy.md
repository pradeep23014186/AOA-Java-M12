
# EX 1C Job Sequencing using Greedy Approach
## DATE: 22/04/2026
## AIM:
To write a Java program to for given constraints.
You're given N jobs, each with:

A unique jobId

A deadline (by which it must be completed)

A profit (earned only if completed on or before the deadline)

Each job:

Takes exactly 1 unit of time

Only one job can be done at a time

Your goal is to maximize total profit while completing the maximum number of jobs possible within their deadlines.

## Algorithm
1. Start the program and read the number of jobs along with their job ID, deadline, and profit.
2. Sort all jobs in descending order based on profit.
3. Find the maximum deadline and create an array to keep track of free time slots.
4. For each job, check for an available slot from its deadline backwards. If a free slot is found, assign the job, increase the job count, and add its profit to the total profit.
5. Print the total number of jobs completed and the maximum profit earned, then stop the program.   

## Program:
```
Program to implement Reverse a String
Developed by: Krishna Prasad S
Register Number: 212223230108
```
```java
import java.util.*;

public class JobScheduling {

    static class Job {
        int id, deadline, profit;

        Job(int id, int deadline, int profit) {
            this.id = id;
            this.deadline = deadline;
            this.profit = profit;
        }
    }

    public static int[] jobScheduling(Job[] jobs, int n) {
        Arrays.sort(jobs, (a, b) -> b.profit - a.profit);
        int maxDeadline = 0;
        for (Job job : jobs) {
            maxDeadline = Math.max(maxDeadline, job.deadline);
        }
        boolean[] slot = new boolean[maxDeadline + 1];

        int countJobs = 0;
        int totalProfit = 0;
        for (Job job : jobs) 
        {
            for (int j = job.deadline; j > 0; j--) 
            {
                if (!slot[j]) 
                {
                    slot[j] = true;
                    countJobs++;
                    totalProfit += job.profit;
                    break;
                }
            }
        }

        return new int[]{countJobs, totalProfit};
    }

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int n = sc.nextInt();
        Job[] jobs = new Job[n];

        for (int i = 0; i < n; i++) {
            int id = sc.nextInt();
            int deadline = sc.nextInt();
            int profit = sc.nextInt();
            jobs[i] = new Job(id, deadline, profit);
        }

        int[] result = jobScheduling(jobs, n);
        System.out.println(result[0] + " " + result[1]);
    }
}

```

## Output:

<img width="374" height="420" alt="output3" src="https://github.com/user-attachments/assets/316de8b6-8e4a-4d4d-9e95-90ab838f227e" />


## Result:
The program successfully implemented and the expected output is verified.
