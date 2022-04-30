# **Second Report Week 4**
## Pick three code changes which fixed the bugs in lab 3. 
### Change 1
* Below is the screenshot for the first change.

[01]: change-0.PNG
![change 1][01]

* This links to the test files which were resolved using the above change. [<Test File 6>](https://github.com/Atch19/markdown-parser/blob/main/test-file6.md).

* The image below shows the symptom of the failure-inducing input running on a version of MarkdownParse before the above change was implemented. 


[04]: errorPics.PNG
![ErrorWithOutChange2][04]


(Ignore the printed file name at the bottom, that was a new print statement made for testing purposes). 

* Although calling markdownParse on test-file6 yielded a result ([page.com]), it was incorrect, therefore it was a symptom of the bug. The input file indicates that page.com is the source for an image, but the MarkdownParse program was created to find the links, not images. Therefore the bug was due to the program not being able to recognize image references and links. The fix was to implement a conditional if statement to exclude link-type objects with the exclamation point preceding. 


***



### Change 2
* Below is the screenshot for the second change. (The change is only the added conditional)

[02]: change-1.PNG
![change 1][02]
* This links to the test files which were resolved using the above change. [<Test File 2>](https://github.com/Atch19/markdown-parser/blob/main/test-file2.md)[<Test File 7>](https://github.com/Atch19/markdown-parser/blob/main/test-file7.md)[<Test File 8>](https://github.com/Atch19/markdown-parser/blob/main/test-file8.md).

* The image below shows the symptom of the failure-inducing input running on a version of MarkdownParse before the above change was implemented. 

[06]: error2.PNG
![ErrorWithOutChange3][06]

* The bug present in the code was the inability of the code to stop if there was a bracket or a parenthesis which lacked a complementary one. This resulted in the symptom, which was a Java Heap Error, clearly resulting because the while loop could not stop. As stated previously the input file lacked complementary brackets or parenthesis which caused the program to error. The fix that we implemented was to break the loop if there was a lacking parenthesis. Therefore this fix was implemented where we check if any of the four elements of a link arn't present in the markdown test input, if any one of these was not found, the loop would break. 

***

### Change 3
* Below is the screenshot for the third change. (The change is only for the movement of the currentIndex variable)

[03]: change-2.PNG
![change 2][03]

* This links to the test files which were resolved using the above change. [<Test File 3>](https://github.com/Atch19/markdown-parser/blob/main/test-file3.md)[<Test File 4>](https://github.com/Atch19/markdown-parser/blob/main/test-file4.md).

* The image below shows the symptom of the failure-inducing input running on a version of MarkdownParse before the above change was implemented. 

[05]: error3.PNG
![ErrorWithOutChange4][05]
* The relationship between the bug, the symptom, and the input file was that the symptom was a out of bounds issue, the bug was clearly some part of the program that referred to an index which was outside the acceptable bounds, and both of the input files lacked a link. The fix we implemented was to move the last statement and the second to last conditional places, thereby removing the index call on an inappropriate locaton. 


