# Lab 5 Report - Polishing the Auto-grader Bash Script
For the final lab, I opted to revise the auto-grader bash script from Week 6 to get a better understanding of JUnit testing and other useful functions within a bash script.

Usage: `bash grade.sh <link to student submission repository>`

## Previous Version
* Very simple: calculated grade as pass or fail using the results from the JUnit output.
<img width="790" alt="Screenshot 2023-03-13 at 5 38 51 PM" src="https://user-images.githubusercontent.com/122574417/224865110-5c7d87c5-5cb4-49aa-b8d3-c882090ee93e.png">

## Updated Version
* Allows for usage of both Darwin and Linux terminal instances.
* Determines a letter grade by comparing the number of tests ran to number of failures.
* Outputs JUnit results when failures occur.
* [Link to updated grade.sh](https://github.com/bretdubois/grader-review-ryan-izad/blob/main/grade.sh)

### Examples of Usage
* [Same starter code from lab 3 (Fail)](https://github.com/ucsd-cse15l-f22/list-methods-lab3)
<br> ![image](https://user-images.githubusercontent.com/122574417/224878251-243f279c-f0aa-44d6-9d0f-c1d3cb8ce94a.png)
***

* [Corrected methods (100%)](https://github.com/ucsd-cse15l-f22/list-methods-corrected)
<br> ![image](https://user-images.githubusercontent.com/122574417/224878192-6cd0c844-910a-406c-a103-c2933da8d2bc.png)
***

* [Incorrect file name (Could not find ListExamples.java)](https://github.com/ucsd-cse15l-f22/list-methods-filename)
<br> ![image](https://user-images.githubusercontent.com/122574417/224878333-d812423d-b50a-4df7-94c2-fb9878668422.png)
***

* [Incorrect syntax (Causes compile error)](https://github.com/ucsd-cse15l-f22/list-methods-compile-error)
<br> ![image](https://user-images.githubusercontent.com/122574417/224878142-7acaa4c8-3a6e-493e-bfb9-a65f295193da.png)
