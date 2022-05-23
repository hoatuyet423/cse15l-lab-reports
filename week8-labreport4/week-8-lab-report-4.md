# LAB REPORT 4 LAB 8

This is Jenny Quach Lab Report 4 for week 8. My PID is A16796954.

## Expected Ouput: 
- Snippet 1: ```[`google.com, google.com, ucsd.edu]```
- Snippet 2: ```[a.com, a.com(()), example.com]```
- Snippet 3: ```[https://www.twitter.com, https://sites.google.com/eng.ucsd.edu/cse-15l-spring-2022/schedule, https://cse.ucsd.edu/]```

## My Repo
- The repo of my markdown: [here](https://github.com/hoatuyet423/lab5-repo.git)
- The Junit Test that I have for this code: ![image](/images/myRepoTestCode.png)
- The Junit messgae after I run the test: ![image](/images/myRepoTestMessage.png)
- The code have some failures and didn't work as expected

## Reviewed Repo
- The repo of the group I reviewed: [here](https://github.com/Barakar13/markdown-parser.git)
- The Junit test that I have for this code: ![image](/images/reviewedRepoTestCode.png)
- The Junit messgae after I run the test: ![image](/images/reviewedRepoTestMessage.png)
- The code have some failures and didn't work as expected

## Questions & Answers:
1. Yes, I can make a small change to check for the symbol "`" and that should make the code run correctly as the code if mess up because it confused with the symbol interfacing between the brackets and mess up the text file. I can make my code either ignore the symbol when it went through the file or make it treat the symbol as it function to make block of code. Although making it does it own function may be a bit of works to do. 
2. Yes, i think this can be change in around 10 lines of code as we can check if the clode brackets is corresponding to the correct open brackets, not just stop at any random brackets. Eventhough i think it can be done with a small change for snippet 2 specificly. I think this might be a big change if we want to put this to be more perfect for all the same kind of error. We can use stack to make the brackets match well to each other and improve more on the code. 
3. Yes, I think this can also be done in small changes as we can just check for the new line with the "\n". But there will be 2 changes to be made. First, we need to get rid of the new line when we get the link inside the parenthesis. Second, we will need to end the checking loop after each sentence, as the code we have right now continue to check for what inside the parenthesis when the close parenthesis is in the wong place at the very end of the text. We need to check for line per line by cutting of the loop after every new line. 