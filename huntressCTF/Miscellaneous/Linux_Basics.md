### Challenge description

Welcome to Linux Basics!

You're expected to answer a series of questions to get the flag.
To view the questions, and answer them, you'll use the `answer` tool.
- Display questions: `answer`
- Answer a question: `answer x` where `x` is question number. 

### Solution

We connect and answer the questions and get the flag. Here are the asnwers:

```
Question 0: What's your home directory?
/home/user

Question 1: Search the man pages. What command would you use to generate random permutations?
shuf

Question 2: On what day was /home/user/myfile.txt modified? Use the date format 2019-12-31
1997-08-29

Question 3: How big is /home/user/myfile.txt, in kilobytes? Round to the nearest whole number.
22

Question 4: What user owns the file /home/user/myfile.txt
root

Question 5: What's the 3-digit octal permissions of the file /home/user/myfile.txt? (e.g 777)
754

Question 6: What is the user id of 'admin'?
1338

Question 7: There is a user 'john' on the system. Can they write to /home/user/myfile.txt? (yes/no)
no

Question 8: Can the 'admin' user execute /home/user/myfile.txt? (yes/no)
yes

Question 9: Which user on the system, except for you, root, admin and john, can execute /home/user/myfile.txt?
rose

Question 10: /home/user/myfile.txt looks like a txt file, but it actually isn't. What kind of file is it?
jpeg
```
flag{8873fe66f8e7a6019d7d71261864f6c5}