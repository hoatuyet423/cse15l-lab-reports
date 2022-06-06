# LAB REPORT 5 WEEK 10

This is Jenny Quach Lab Report 4 for week 8. My PID is A16796954.

## STRATEGY
- The strategy I used is that I print all the test from the provided markdown and find the one look stand out and different, then compare it with my own code. I used the map in my main function to get all the results print out for the links in the provided markdown. And on my end, I just replace or create a new file to test out and see the result based on my markdown

## TEST 1
- [test-file-link](/587.md)
- For this file. the provided implement is inccorrect because it is an image link not a url link so it should print out `[]` not print out a blank array `[/url "title"]`.
- epxected output: `[]`
- ![out put for my actual output](/images/test1Own.png)
- ![out put for provided actual output](/images/test1Provided.png)
- I think the problem of the provided code is that it couldn't keep track of the "!". In the function getLinked where it take in markdown as argument, we should included something that also take care of the notation "!"
- ![fixed](/images/test1Fixed.png)

## TEST 2
- [test-file-link](/511.md)
- For this file. the provided implement is correct and my implement is wrong. becuase this is a url just with many [] inside but it is all corresponding to each other. Therefore it should be `[/uri]` not `[]`
- expected implement: `[/uri]`

- ![out put for my actual output](/images/test2Own.png)
- ![out put for provided actual output](/images/test2Provided.png)
- I think my problem is that i dont check the duplicates [] and it mess up the code. In the loop, i should have check if the [] is corresponding to each other or not
- ![fixed](/images/test2Fixed.png)