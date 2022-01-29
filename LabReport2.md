# Lab Report 2
### This Lab Report consists of explaining 3 changes the team “Starfish” did to the code  ``` MarkdownParse.java ``` in order to fix some of the problems that happened during some edge cases.

## First Fix: No Commands given in the Arguments
We noticed that whenever we did not include any arguments in the command line, the program would crash and throw a
```
ArrayIndexOutOfBoundsException
```

