# DEBUG REPORT

*Hi, this is Jenny Quach. My PID is A16796954. This is my week 4 lab report 2*

This report will contain 3 bugs and the analysis of the bug 

## 1. When there is a parentheses in the middle of the link
- Images of the committed changes: 
![images](/images/fixedParenInMiddleCommit.png)
- Test fail that lead to the failure-inducing input:
[here](/test1.md)
- The symptom of this failure-inducing if that it cause an infinite loop of `[rando(]`
- Becuase the input have an extra parentheses in the middle of the link. From the symptom of an infinite loop, we can tell that there is something wrong the loop condition that cause the loop never stop, and we can use that symptom to analyse our bug. By adding print statemnt, we can tell that the becuase the currentIndex (which control the condition of the loop) only change based on closeParen, and there is an extra closeParen in the middle, meaning that adding it will never read the length of themn the markdown becuase the close Paren if not final. Also inside every loop, the open/close Bracket index also got reinitialize every single time, make no change to meaning that currentIndex and other index that based on that will also have no change. We can fix this bug by initialize the variables of those index outside the loop, and will stop the loop if any of those variable (oopen/close Bracket and open/close Parentheses) can't no longer be found. 

## 2. When add a new line after the link statement

- Images of the committed changes: 
![images](/images/fixedNewLineCommit.png)
- Test fail that lead to the failure-inducing input:
[here](/test2.md)
- The symptom of this failure-inducing if that it cause an infinite loop
- Becuase the input create an extra line in the end of the file. From the symptom of an infinite loop, we can tell that there is something wrong the loop condition that cause the loop never stop, and we can use that symptom to analyse our bug. On our code, we have a bug that we will loop until the currentIndex become greater than the markdown length and we only change the currentIndex based on the incrementing from the last closeParen, currentIndex never actually read the length of the markdown becuase there is one extra index from the new line. Therefore, to fix this bug, we added an if statement that check for the newline and break the code when there is one. 

## 3 When there is no link in the file 
- Images of the committed changes: 
![images](/images/fixedNoLinkCommit.png)
- Test fail that lead to the failure-inducing input:
[here](/test3.md)
- The symptom of this failure-inducing if that it cause an IndexOutOfBoundException
- Becuase the input have no link inside it and the symptom show IndexOutOfBound, we can tell that the bug is that the program is checking for something that is not inside the file. From our code, we can see that we got the index of close/open Bracket and close/open Parentheses. Since the input is blank, the index that return for those variables will be -1 and since the return result is based on the index of those variables, when we call for a substring of a nonexist input, it will cause IndexOutOfBoundException, which is the symptom that we get. To fix this bug, we cna add to the if statement to make the loop break if we cant find any close/open Bracket or close/open Parantheses 
