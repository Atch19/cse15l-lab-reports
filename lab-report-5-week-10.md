# **Fifth Report Week 10**

## **Questions**
***
### **How you found the tests with different results (Did you use vimdiff on the results of running a bash for loop? Did you search through manually? Did you use some other programmatic idea?)**
To find the tests with the different results, we ran both of the programs on all the tests, during which we outputted all the results to a new file (seperate one for each one of the program versions). We then moved both files to the same directory, then we used vimdiff to compare both of them. After which we manually searched through the vimdiff to locate the differences.


### **Provide a link to the test-file with different-results**
Test that had different results: [Link to test (file 194)](https://github.com/nidhidhamnani/markdown-parser/blob/main/test-files/194.md)

### **Describe which implementation is correct, or neither if both give the wrong output**
Both implementations were wrong, our implementation failed to produce any output and the implementation that we were provided with gave "url" as the output but that was wrong, because when I ran the code in a markdown language compiler, the expected link was actually "my_(url)"

Actual output: 

left side = ours "[]", right side = implementation we were given. "[url]"

[i]: test194.PNG
![3-1][i]

Expected output: 
"my_(url)"

[i2]: expected.PNG
![3-1][i2]

### **Describe the bug**
This difference in programs isn't actually a bug with our programs. When I looked into the testfile I found that it used a different syntax for storing and projecting links. An explanation of the different syntax is screenshotted from [External Website daringfireball.net](https://daringfireball.net/projects/markdown/syntax#link).

[i3]: explanation.PNG
![3-1][i3]

Raw testfile 194

[i4]: 194raw.PNG
![3-1][i4]

This different syntax isn't exactly covered by our programs as we search for [] and ().
However if we were to "fix this bug" and extend coverage to support this type of link integration we would insert a if statement where the red arrow is pointing on our version of the code. This if statement would search if there is a ":" after the closing square braket, and in that case consider everything up to the elements: " ' (, and after ":" a link. (Although there needs to be a more serious method of detecting the difference between these elements in links compared to the title)

[i5]: bugfix.PNG
![3-1][i5]