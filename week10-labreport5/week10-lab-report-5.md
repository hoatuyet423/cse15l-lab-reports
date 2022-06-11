# LAB REPORT 5 WEEK 10

This is Jenny Quach Lab Report 4 for week 8. My PID is A16796954.

## STRATEGY
- The strategy I used is that I print all the test from the provided markdown and and my code with the provided test files. For the provided code, I used the map in my main function to get all the results print out for the links in the provided markdown by using key and the associated value of the key. Then I check for implementation that is stand out and since I know how my implementation work, I can quickly spot out the special cases. Then compared back to my code. And on my end, I will just import the file into my folder and then run the test file to check if the results is different or not

## TEST 580
- This is the link to the test file: [test-file-link](/580.md)
- Expected Output is `[]` Since there is it is an image link and no link provided, the output should be blank as shown in vscode preview as below: ![image](/images/test1ExpectedOutput.png)
- The output from the provided implementation is `[/url]`: ![image](/images/test1Provided.png)
- The out put for my implemenatation is `[]`: ![image](/images/test1Own.png)
- From the observation above, we can conclude that for test file 580, my implementation provided the correct output while the implementation from the provided code provided the wrong output.
- I think the problems with the provided code is that it didn't track for the notation `!` in front of the open bracket `[` which indicate that the link is an image not an url link. Therefore, it will just take anything that have the format `[]()` eventhough there is some special notation in front it. 
- I believe that we can fix this by adding an code block with an if statement inside the loop when we try to read through to the whole file. We can add an if statement to check if there is any `!` to be specific or if the is any special notation before the open bracket to see if it is a url link or just an image link. 
![image](/images/test1Fixed.png)


## TEST 511
- This is the link to the test file: [test-file-link](/511.md)
- Expected Output is `[/uri]` as shown in vscode preview as below: ![image](/images/test2ExpectedOutput.png)
- The output from the provided implementation is `[/uri]`: ![image](/images/test2Provided.png)
- The out put for my implemenatation is `[]`: ![image](/images/test2Own.png)
- From the observation above, we can conclude that for test file 511, my the provided markdown parse code give the correct output while the implementation from my group give the wrong output. 
- I think the bug with my implementation is that I didn't check for the open and close bracket correctly. For my code, it will just break out of the loop when it noticed a bracket that did fit into the template `[]()`. However, tittle of the link should work as long as the open bracket `[` have a correct corresponding close bracket `]`. Despite having some bracket in between, as long as all the bracket are correctly correspponding to each other, there should be no conflict. 
- To fix this bug, I will have to implement a algorithm to check and find the corresponding close and open pair of brackets and make sure they are correctly ordered. I will need to fix the if else statement where I break the loop when there is invalid bracket (when bracket is not founded in the correct order).
![image](/images/test2Fixed.png)