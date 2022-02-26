# Lab Report 4
<br/>

## [Link to my repository](https://github.com/Jivan132/markdown-parse)
## [Link to the repository that we reviewed](https://github.com/Stocktocon/markdown-parse)

<br/>

## Expected Output:
**Snippet 1:** ``` ["`google.com", "google.com", "ucsd.edu"] ```

**Snippet 2:** ```["a.com", "a.com(())", "example.com"]```

**Snippet 3:** ```["https://twitter.com", "https://ucsd-cse15l-w22.github.io/", "https://cse.ucsd.edu/"]```


## Tests:
![Tests](https://github.com/Jivan132/cse15l-lab-reports/blob/main/Lab-Report-4/Photos/Snippet%20Tests.jpg?raw=true)

<br/>

## Own markdown-parse Tests
![Own results 1](https://github.com/Jivan132/cse15l-lab-reports/blob/main/Lab-Report-4/Photos/Own%20Tests%20Fail%201.jpg?raw=true)

![Own results 2](https://github.com/Jivan132/cse15l-lab-reports/blob/main/Lab-Report-4/Photos/Own%20Tests%20Fail%202.jpg?raw=true)

>The tests for the Snippet 1, Snippet 2, and Snippet 3 failed when I tried to run them against my version of markdown-parse. This can be seen in the photo that shows the terminal with the expected values and the actual values (```1) testSnippet1(MarkdownParseTest)```, ```2) testSnippet2(MarkdownParseTest)```, ```3) testSnippet3(MarkdownParseTest)```), as well with the ```Tests run: 3,  Failures: 3``` line.

## Reviewed version of markdown-parse Test:
![Reviewed results 2](https://github.com/Jivan132/cse15l-lab-reports/blob/main/Lab-Report-4/Photos/Reviewed%20version%20tests.jpg?raw=true)
>The reviewed code failed to pass the tests for Snippet 1, Snippet 2, and Snippet 3. This can be seen on the output of the terminal (```1) testSnippet1(MarkdownParseTest)```, ```2) testSnippet2(MarkdownParseTest)```, ```3) testSnippet3(MarkdownParseTest)```), as well with the ```Tests run: 3,  Failures: 3``` line.


## Questions:
- *Do you think there is a small (<10 lines) code change that will make your program work for snippet 1 and all related cases that use inline code with backticks? If yes, describe the code change. If not, describe why it would be a more involved change.*

I think there could be a small fix to fix the first URL in snippet 1 ``` `[a link`](url.com)``` and the second one ``` [another link](`google.com)` ```. This could  be done by just checking for backticks before and after the link. However, I think it could be a little bit more complicated for the other links. This is because we need to take into account the brackets inside of that link.

- *Do you think there is a small (<10 lines) code change that will make your program work for snippet 2 and all related cases that nest parentheses, brackets, and escaped brackets? If yes, describe the code change. If not, describe why it would be a more involved change.*

I do not think there is a small code change that we can do in the code to make the program work for snippet 2. During one of the labs we actually ran into this error and tried different ways to salve it. Most of them included complicated loops and other type of counters. Furthermore, in class we did something similar to this in which we also needed more than 10 lines code.

- *Do you think there is a small (<10 lines) code change that will make your program work for snippet 3 and all related cases that have newlines in brackets and parentheses? If yes, describe the code change. If not, describe why it would be a more involved change.*

I do not know any solutions that involves less than 10 lines of code for snippet 3. Since the URLs include newlines, you need to take into account that in the code. I do not know how to tackle this specific problem, but I would try to search a way to make the code “ignore” those newlines so it can treat it as a normal link.
