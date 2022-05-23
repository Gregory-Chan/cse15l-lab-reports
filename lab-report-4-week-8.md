# Lab Report 4
# Snippet 1
Below is the markdown file for the first snippet
```
`[a link`](url.com)

[another link](`google.com)`

[`cod[e`](google.com)

[`code]`](ucsd.edu)
```
Using VSCode's markdown preview, the result of running markdown-parse on this markdown file should be  ```[`google.com, google.com, ucsd.edu]```.

I added the following tests to my and the other group's markdown-test-file.

The test in my file:
![image](Lab4_Images\my_test_snippet1.PNG)

The test in the other group's file:
![image](Lab4_Images\review_test_snippet1.PNG)

The results of both tests are shown below:

The test in my file:
![image](Lab4_Images\my_output1.PNG)

The test in the other group's file:
![image](Lab4_Images\review_output1.PNG)

In outputs of both my and the other group's implementation were the same which was ```[url.com, `google.com, google.com]``` which was not the expected output so both implementations failed the test.

I do believe that there is a small code change that I can make to fix this issue. If I add to my program to check the start and end of the backticks and disregard any open or close bracket or parenthesis etc. inside the backticks. As a result, all brackets and parenthesis inside the backticks should be ignored so that the correct output can be produced.

# Snippet 2
Below is the markdown file for the second snippet
```
[a [nested link](a.com)](b.com)

[a nested parenthesized url](a.com(()))

[some escaped \[ brackets \]](example.com)
```

Using VSCode's markdown preview, the result of running markdown-parse on this markdown file should be  `[a.com, a.com(()), example.com]`.

I added the following tests to my and the other group's markdown-test-file.

The test in my file:
![image](Lab4_Images\my_test_snippet2.PNG)

The test in the other group's file:
![image](Lab4_Images\review_test_snippet2.PNG)

The results of both tests are shown below:

The test in my file:
![image](Lab4_Images\my_output2.PNG)

The test in the other group's file:
![image](Lab4_Images\review_output2.PNG)

The output for my implementation was  `[a.com, a.com((, example.com]` which is missing the 2 closing parentheses at the end of a.com(( so it failed the test.

The output for the other group's implementation was `[]` which is not the expected output so it failed the test.

I do believe that there is a small code change that I can make to fix this issue. Since the output for my implementation is close to the expected output, it is just missing the 2 closing parentheses, if I change my code to check for pairs of parentheses instead of just checking for the next closing parenthesis. This should fix the problem.

# Snippet 3
Below is the markdown file for the third snippet
```
[this title text is really long and takes up more than 
one line

and has some line breaks](
    https://www.twitter.com
)

[this title text is really long and takes up more than 
one line](
https://sites.google.com/eng.ucsd.edu/cse-15l-spring-2022/schedule
)


[this link doesn't have a closing parenthesis](github.com

And there's still some more text after that.

[this link doesn't have a closing parenthesis for a while](https://cse.ucsd.edu/



)

And then there's more text
```

Using VSCode's markdown preview, the result of running markdown-parse on this markdown file should be  `["https://www.twitter.com", "https://sites.google.com/eng.ucsd.edu/cse-15l-spring-2022/schedule", "https://cse.ucsd.edu/"]`.

I added the following tests to my and the other group's markdown-test-file.

The test in my file:
![image](Lab4_Images\my_test_snippet3.PNG)

The test in the other group's file:
![image](Lab4_Images\review_test_snippet3.PNG)

The results of both tests are shown below:

The test in my file:
![image](Lab4_Images\my_output3.PNG)

The test in the other group's file:
![image](Lab4_Images\review_output3.PNG)

The output for my implementation was  `[https://www.twitter.com, https://sites.google.com/eng.ucsd.edu/cse-15l-spring-2022/schedule, github.com
And there's still some more text after that.
[this link doesn't have a closing parenthesis for a while](https://cse.ucsd.edu/]` which is not the expected output so it failed the test.

The output for the other group's implementation was `[]` which is not the expected output so it failed the test.

I do believe that there is a small code change that I can make to fix this issue. Currently, my program checks for an open parenthess and searches for the next close parenthess and since this markdown file contains a link that doesn't have a closing parenthesis but there is another link after it that does have a closing parenthesis, my program takes that as a massive link. So, if I implement a change similiar to the change for snippet 2 where I check for if there is a pair of brackets when getting the link and if there is, the program should disregard the previous link it was looking for and start a new search following this pair of brackets. This should fix the problem.