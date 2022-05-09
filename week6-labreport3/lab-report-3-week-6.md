# LAB REPORT 3 FOR WEEK 6

Hi, this is Jenny Quach lab report 3. My PID is A16706054. 

## 1. Streamlining ssh Configuration
- I was able to edit the config file from ssh on vscode using the extention from vscode
![image](/images/img1-1.png)
- By adding those lines into my ~/.ssh/config. I was able to log into my remote server by just using the alias ieng6 instead of the whole username like I used to do. 
![image](/images/img1-2.png)
- I added a file name hello.txt into the folder of week6-labreport3 and then copy that file into the ssh server using my alias "ieng6" 
![image](/images/img1-3.png)

## 2. Setup Github Access from ieng6
- My public key on github
![image](/images/img2-1.png)
- My private key at my local computer
![image](/images/img2-2.png)
- I create a new file in the repo to make some change to the repo, then commit and push it in ieng6
![image](/images/img2-3.png)
- Link to the commit on github: [here](https://github.com/hoatuyet423/cse15l-lab-reports/commit/9c78067287d6a340a890fc0fe3a3bcc37cf39869)

## 3. Copy whole directories with scp -r
- I named my current markdown-parse as lab5-repo so I will copy that instead. 
![image](/images/img3-1.png)
- I am able to run the junit test inside of my ieng6 account
![image](/images/img3-2.png)
- I was able to combine everything into one line (copy, log into ssh server then run the junit test)
![image](/images/img3-3.png)
