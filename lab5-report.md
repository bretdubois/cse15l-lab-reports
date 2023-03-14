# Lab 5 Report - Polishing the Auto-grader Bash Script
For the final lab, I opted to revise the auto-grader bash script from Week 6 to get a better understanding of how to use various functions within a bash script.

Usage: `bash grade.sh <link to student submission repository>`

### Previous Version
Very simple, calculated grade as pass or fail using the results from the JUnit output.
<img width="790" alt="Screenshot 2023-03-13 at 5 38 51 PM" src="https://user-images.githubusercontent.com/122574417/224865110-5c7d87c5-5cb4-49aa-b8d3-c882090ee93e.png">

### Updated Version
Allows for usage of both Darwin and Linux terminal instances.
Determines a letter grade using the difference in failures compared to tests ran.

