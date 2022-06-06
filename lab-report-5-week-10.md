# Lab Report 5
# First Test File
I used vimdiff to find that the output from test file 194 was different. Here is a link to the [file](https://github.com/Gregory-Chan/markdown-parser/blob/main/test-files/194.md).

In my Implementation the output was:
![image](Lab5_Images\Test_1_my_output.PNG)
The output of the provided markdown parser was:
![image](Lab5_Images\Test_1_other_output.PNG)

I believe my implementation is correct since there are some characters between the brackets and the first parenthesis so it should not be counted as a list.

# Second Test File
I used vimdiff to find that the output form test file 22 was different. Here is a link to the [file](https://github.com/Gregory-Chan/markdown-parser/blob/main/test-files/22.md)

In my Implementation the output was:
![image](Lab5_Images\Test_3_my_output.PNG)
The output of the provided markdown parser was:
![image](Lab5_Images\Test_3_other_output.PNG)

I believe that both implementations are incorrect. Using the CommonMark demo site, the expected output should be `[bar*]`. This is because there can be no space in a link.

# Fix For The First Test File
I believe the problem in the code is that it is not checking if there is anything inbetween the brackets and the parentheses and instead simply find the next pair of brackets.
Here is the image of the code that can be changed:
![image](Lab5_Images\Code.PNG)
I think that an if statement could be added after line 65 to check if the index of openParen is 1 greater than nextCloseBracket and it is then continue but if it isn't then this link should not be added.