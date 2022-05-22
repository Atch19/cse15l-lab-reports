# **Forth Report Week 8**

## Links
[Link to our repo](https://github.com/Atch19/markdown-parser)

[Link to the repo we reviewed](https://github.com/DanUCSD/markdown-parser)

***

## **Test 1**
### **Our Implementation**
***
**What it should output:**
 ['google.com, google.com, ucsd.edu]

 *This result was determined by what markdown considers a link to a website, not exactly in the spirit of the program which determines links based on the relative position to [] and ()*


**What it looks like:**


[t1]: t1.PNG
![3-2][t1]

**Output:**
Did not pass:

[r1]: r1.PNG
![3-2][r1]


### **Their Implementation (the one we reviewed)**
***
**What it should output:**
 ['google.com, google.com, ucsd.edu]

 *This result was determined by what markdown considers a link to a website, not exactly in the spirit of the program which determines links based on the relative position to [] and ()*

**What it looks like:**

[t1]: t1.PNG
![3-2][t1]

**Output:**
Did not pass:

*side note: I don't exactly know why their program gave no output for each test, but I assume it has something to do with their algorithm which was rather different than ours and others I have seen*

[r4]: r4.PNG
![3-2][r4]

***

## **Test 2**
### **Our Implementation**
***
**What it should output:**
 [a.com, a.com(()), example.com]

 *This result was determined by what markdown considers a link to a website, not exactly in the spirit of the program which determines links based on the relative position to [] and ()*


**What it looks like:**

[t2]: t2.PNG
![3-2][t2]

**Output:**
Did not pass:

[r2]: r2.PNG
![3-2][r2]

### **Their Implementation (the one we reviewed)**
***
**What it should output:**
 [a.com, a.com(()), example.com]

 *This result was determined by what markdown considers a link to a website, not exactly in the spirit of the program which determines links based on the relative position to [] and ()*

**What it looks like:**

[t2]: t2.PNG
![3-2][t2]

**Output:**
Did not pass:

*side note: I don't exactly know why their program gave no output for each test, but I assume it has something to do with their algorithm which was rather different than ours and others I have seen*

[r5]: r5.PNG
![3-2][r5]

***

## **Test 3**
### **Our Implementation**
***
**What it should output:**
 [https://sites.google.com/eng.ucsd.edu/cse-15l-spring-2022/schedule]

 *This result was determined by what markdown considers a link to a website, not exactly in the spirit of the program which determines links based on the relative position to [] and ()*

**What it looks like:**

[t3]: t3.PNG
![3-2][t3]


**Output:**
Did not pass:

[r3]: r3.PNG
![3-2][r3]


### **Their Implementation (the one we reviewed)**
***
**What it should output:**
 [https://sites.google.com/eng.ucsd.edu/cse-15l-spring-2022/schedule]

 *This result was determined by what markdown considers a link to a website, not exactly in the spirit of the program which determines links based on the relative position to [] and ()*

**What it looks like:**


[t3]: t3.PNG
![3-2][t3]


**Output:**
Did not pass:

*side note: I don't exactly know why their program gave no output for each test, but I assume it has something to do with their algorithm which was rather different than ours and others I have seen*

[r6]: r6.PNG
![3-2][r6]

***
## **Questions**
### **Do you think there is a small (<10 lines) code change that will make your program work for snippet 1 and all related cases that use inline code with backticks? If yes, describe the code change. If not, describe why it would be a more involved change.**

Yes I think there is a simple fix to this issue which could be under 10 lines of code. We need to implement a if statement before any of these symbols are found []() which detects if there is a cancelling symbol "`". In which case its going to skip the []() symbol. 


### **Do you think there is a small (<10 lines) code change that will make your program work for snippet 2 and all related cases that nest parentheses, brackets, and escaped brackets? If yes, describe the code change. If not, describe why it would be a more involved change.**

No, I think this is a rather complex issue, partly because detecting the closing ")" symbol is extremely hard considering that we are only using the file converted to text. We are going to need to use a decently hard sequence of if statements to find the correct one corresponding to the initial starting "(". My partner and me attempted to solve this issue before and spent over an hour without much progress. In addition, we are going to struggle with nested links as those ones will reqire the program to be capable of storing the information of several links at once. 

### **Do you think there is a small (<10 lines) code change that will make your program work for snippet 3 and all related cases that have newlines in brackets and parentheses? If yes, describe the code change. If not, describe why it would be a more involved change.**

Yes, I think this is an issue that can be resolved in under 10 steps. Partly because the output was almost correct, it just needs to be able to identify a link where there is no closing parenthesis but later it does appear. Technically, this fix shouldn't be needed because the problem is in the markdown rather than the code. But it could be solved where there is an if statement that detects the end of a link (when there is a " " after the text appending the opening "(" this solution will most likely fix the issue.