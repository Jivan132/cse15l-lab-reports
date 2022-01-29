# Lab Report 2
### This Lab Report consists of explaining 3 changes the team “Starfish” did to the code  ``` MarkdownParse.java ``` in order to fix some of the problems that happened during some edge cases.

<br/><br/> 

## First Fix: No Commands given in the Arguments
We noticed that whenever we did not include any arguments in the command line, the program would crash and throw a
```
ArrayIndexOutOfBoundsException
```
![changes fix 1](https://github.com/Jivan132/cse15l-lab-reports/blob/main/photos/Lab_Report2/Changes_Fix1.jpg?raw=true)

> There was no file that induce the failure since the crash came when there were no arguments.

*Symptom of failure-induce error:*
```
Exception in thread "main" java.lang.ArrayIndexOutOfBoundsException: Index 0 out of bounds for length 0 at MarkdownParse.main(MarkdownParse.java:25)
```