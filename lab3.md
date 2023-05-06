# **Lab Report 3 - Researching Commands (Week 5)**
* The task at hand is to select *one* of the bash commands that we learned in lecture: `find`, `less`, `grep`.
* Research 4 different options and give 2 examples using the `./technical` directory that we have been working with.
 
## Chat-GPT!
* Before I select a command to research, I was curious to see how effective Chat-GPT would be in helping me get the information for these commands.
* So I did exactly just that:
 
### Prompt:
![Image](images/Prompt.png)
 
### Chat-GPT Response:
#### `Grep`:
![Image](images/grep.png)
####  `Find`:
![Image](images/find.png)
#### `Less`:
![Image](images/less.png)
 
* Even though Chat-GPT doesn't give us every option, I still feel like its pretty interesting to see!

## **Grep:**
* For this lab, I decided to go with the `grep` command because it was the most confusing to me and so I want to tackle it to get a better understanding!
* From earlier, the commands that seemed interesting to me were `-v`, `-w`, `-n`, and `-m`
* **NOTE:** I did ask Chat-GPT again for a list of ALL options or flags using grep. To prevent this write-up from being too lengthy of Chat-GPT screenshots, I will briefly just say that only `-m` is the only 'new' option obtained from this search.

### `-v`
* According to AI, this option **inverts** our grep search, in which it will show lines that **don't** match the given pattern.
#### Prior Work: 
* *Note that I added ... to make it less lengthy!*
`wc -l technical/911report/*.txt | sort
    108 technical/911report/preface.txt
    603 technical/911report/chapter-10.txt
  . 
  .
  .
   3159 technical/911report/chapter-3.txt
   3237 technical/911report/chapter-13.5.txt
  25728 total`
* I used the recently learned "Pipe" command to take the output from `wc` and used it as input to `sort`
* We have 25728 total lines from all the text files from 911report.
##### Example 1:
`$ grep -v "murder" technical/911report/*.txt | wc -l | sort
25721`
* Note that I used the "Pipe" command again to use my `grep` output as an input into `wc` and then into `sort`. I find this technique to be very useful!
* Here, we use the `-v` option so that we can count the number of lines that do **not** contain "murder". It turns out we can deduce that 7 lines contain the word "murder". This command can be useful in filtering out what we do not want.

##### Example 2: 
`$ grep -v -e "murder" -e "blood" -e "police" -e "poison" -e "fire" technical/911report/*.txt | wc -l | sort
25422`
* Now here is a stronger example. Suppose that I wanted lines that do not contain "murder", "blood", "police", "poison", or "fire". Then, I'd be able to use the `-e` command along with `-v` in order to make a stronger filter to give me what I want. In this case, we can see that there are 306 lines that contain either one or more of these words. Therefore, `-v` is a very powerful tool that can be used in combination with other commands to create a filter of what a user might not want in an output.

### -`w`
* Our good friend Chat-GPT describes this option as a way to match **whole words** as opposed to partial matches.




### `-n`
* AI says that this option can be used in our grep search to show each matching line's **line number** in the file.




### -`m NUM`
* Chat-GPT describes this option as a way to tell grep to stop searching after a certain number of matches.



