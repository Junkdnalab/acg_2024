# Assignment 2: More unix commands and a little git

```put all commands and terminal output in triple backquotes```

## Git

1. Either download or create a copy of this file in the repository we created in class. "Add" the file by checking the appropriate box in the git tab of rstudio. Then commit and push to remote. Make a commit message that records the fact that this file has not been worked on (by you) yet.

```my answer : I had to re-configure my account to add assignment 02 to my terminal i did the following:
1. gh autho login
2. Pressed enter
3. collected the verification code and clicked on the link put in the code 
4 File
5 Existing directory selected the following folder "acg_2024_fork"
6 Create project
7. Selected teh assignments folder
8. Assignment_02.md
9. commit
10. added "incomplete hw"
11. clicked on pushed```


2. Open the newly created homework file in your homework repo within rstudio. Complete the rest of this assignment. When you're finally ready to finally hand it in, add, commit (with appropriate message) and push. If you need to make an edit before the deadline, you can repeat the commit cycle making a comment in the commit message. kks

```` See answer in question #1 ""
## Man pages

Nearly every command in GNU has a manual, documentation that tells you all the functions and capabilities of each command that we've been learning about. Naturally, there is a program called `man` to access the manual pages (more commonly "man pages") for each command.

3. Let's use `man` to figure out what some other commands do. Run `man` on the `who` command. What do you think the SYNOPSIS section is for?

```I entered in the terminal lizbeth.Sanchez@5f5e041c8ec6:~/projects/acg_2024$ man who 
I got this response SYNOPSIS and this means; to explore in detail the information and options avaliable for set command for example [option] and [file] futher Synopsis acts a quick guide that shows how to use a command ```


4. Which option of `who` allows you to determine when your system was last rebooted? When was your system last booted? Show the shell interaction inside triple quotes as we did in the previous assignment.

```Lizbeth.Sanchez@5fe041c8ec6:~/projects/acg_2024$ uptime 
```the last time the system was last booted was in 20:47:14 up 43 days, 2:18 ```

5. Using `man`, see if you can determine what the `cut` program does? (no answer required)

```Lizbeth.Sanchez@5fe041c8ec6:~/projects/acg_2024$ man cut 
takes me to the same page as "man who ```


## wc, sort, and cut

6. In a web browser, navigate to the following page on Github, which has lots of example datasets people use for machine learning: https://github.com/EpistasisLab/pmlb/tree/master/datasets
Download the dataset called `breast_cancer` (be exact: there are several breast cancer datasets!). You should have a spread sheet in "tab separated values" format (".tsv"). First take a peek at the data using `less`. Use `head` to display the first line only, paste the output of the terminal interaction below.


```This is what I did 
Lizbeth.Sanchez@5fe041c8ec6:~/projects/acg_2024$ wget https://github.com/Epistasislab/pmlb/blob/master/datasets/breat_canver/breast_cancer.tsv.gz
Lizbeth.Sanchez@5fe041c8ec6:~/projects/acg_2024$ less breast_cancer.tsv.gz
Lizbeth.Sanchez@5fe041c8ec6:~/projects/acg_2024$ head breast_cancer.tsv.gz
{"payload":{"allShortcutsEnabled":false,"fileTree":{"datasets/breast_cancer":{"items":[{"name":"README.md","path":"datasets/breast_cancer/RE```

7. How many fields are there? Which number field corresponds to tumor sizes? Can you write a command to extract this column? Show the command below, but not the output.

```Lizbeth.Sanchez@5f5e041c8ec6:~$ awk -F '\t' '{print NF; exit}' breast_cancer.tsv.gz
number of fields says 1```

```Which number field corresponds to tumor sizes? Ans:2 ```
```Can you write a command to extract this column ? Ans: Lizbeth.Sanchez@5f5e041c8ec6:~$  


8. What does the `wc` command do?

```Answer: the wc command helps for word counting, line, character or byte count```

9. How many lines are there in the dataset? How many words? (show work)

```Lizbeth.Sanchez@5f5e041c8ec6:~$ wc breast_cancer.tsv.gz
command results 0 24 41130 breast_cancer.tsv.gz```



10. How many characters are there in the column 'tumor-size'? (hint: use `cut` to isolate the tumor size column, and a pipe `|` to direct the output of this command to an appropriate call of `wc`) (show work)

```Lizbeth.Sanchez@5f5e041c8ec6:~$ wc -c breast_cancer.tsv.gz 
command results: 41130 breast_cancer.tsv.gz
```Lizbeth.Sanchez@5f5e041c8ec6:~$ cut -f 'tumor-size' breast_cancer.tsv.gz | wc -c ```


11. The `sort` command is very useful. Use the `man` page to determine how you would find all the unique values that "tumor-size" can have in this dataset. Using a strategy similar to the previous problem, what are all the unique values in the tumor-size column? (hint: string together 3 commands with 2 pipes) (show work)
 
```Lizbeth.Sanchez@5f5e041c8ec6:~$ man man 
Lizbeth.Sanchez@5f5e041c8ec6:~$ cat breast_cancer.tsv.gz |cut -f 'tumor-size' 
cat breast_cancer.tsv.gz| head| cut -f "tumor-size```





