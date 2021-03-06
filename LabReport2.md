# Lab Report 2
### This Lab Report consists of explaining 3 changes the team “Starfish” did to the code  ``` MarkdownParse.java ``` in order to fix some of the problems that happened during some edge cases.

<br/><br/> 

## First Fix: No Commands given in the Arguments
We noticed that whenever we did not include any arguments in the command line, the program would crash and throw a
```
ArrayIndexOutOfBoundsException
```
*Screenshot:*
![changes fix 1](https://github.com/Jivan132/cse15l-lab-reports/blob/main/photos/Lab_Report2/Changes_Fix1.jpg?raw=true)

> There was no file that induce the failure since the crash came when there were no arguments.

*Symptom of failure-induce error:*
```
Exception in thread "main" java.lang.ArrayIndexOutOfBoundsException: Index 0 out of bounds for length 0 at MarkdownParse.main(MarkdownParse.java:25)
```
*Description:*
The symptom appears because the program is trying to use the first index of the array ``` args ```. However, since the array ``` args ``` uses the command line arguments to make the array and there are no arguments in the command line, then the array is empty. That means that when the program wants to access the array it causes an ``` ArrayIndexOutOfBoundsException ```.
<br/><br/> 
## Second Fix: If the link is for an image 
We noticed that when the link was an image it returned the link.
*Screenshot:*

![changes fix 2](https://github.com/Jivan132/cse15l-lab-reports/blob/main/photos/Lab_Report2/Changes_Fix2.jpg?raw=true)

*Failure-inducing input file:*

[Link](https://github.com/Jivan132/markdown-parse/blob/main/test-file.md) to the file that caused the failure.

*Symptom of failure-induce error:*
```
[actual-Link.html, https://github.com/Jivan132/cse15l-lab-reports/blob/main/photos/Lab_Report2/Changes_Fix1.jpg?raw=true]
```

*Description:*
The program was taking everything between parentheses as a Link. However, images are also formatted the same way as links. To fix this, you just need to pay attention if there is an “!” before the brackets.

<br/><br/> 
## Third Fix: If the link is for an image 
We noticed that whenever the link was incomplete the program caused an error.

*Screenshot:*

![changes fix 3](https://github.com/Jivan132/cse15l-lab-reports/blob/main/photos/Lab_Report2/Changes_Fix3.jpg?raw=true)

*Failure-inducing input file:*

[Link](https://github.com/Jivan132/markdown-parse/blob/main/test-file2.md) to the file that caused the failure.

*Symptom of failure-induce error:*

```
Exception in thread "main" java.lang.StringIndexOutOfBoundsException: begin 0, end -1, length 8
        at java.base/java.lang.String.checkBoundsBeginEnd(String.java:4601)
        at java.base/java.lang.String.substring(String.java:2704)
        at MarkdownParse.getLinks(MarkdownParse.java:32)
        at MarkdownParse.main(MarkdownParse.java:47)
```

*Description:*
The crash appears whenever the link is not complete. This is caused because the program is expecting the two brackets and the two parentheses, so whenever one is missing the program crashes. We can get around this issue by telling the program that if one of these is missing, do not execute all the code.

<br/><br/> 

---
##### [Link](https://github.com/Jivan132/markdown-parse) to markdown-parse repository