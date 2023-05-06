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
 
```
wc -l technical/911report/*.txt | sort
    108 technical/911report/preface.txt
    603 technical/911report/chapter-10.txt
  . 
  .
  .
   3159 technical/911report/chapter-3.txt
   3237 technical/911report/chapter-13.5.txt
  25728 total
```
* I used the recently learned "Pipe" command to take the output from `wc` and used it as input to `sort`
* We have 25728 total lines from all the text files from 911report.
##### Example 1:
```
$ grep -v "murder" technical/911report/*.txt | wc -l | sort
25721
```
* Note that I used the "Pipe" command again to use my `grep` output as an input into `wc` and then into `sort`. I find this technique to be very useful!
* Here, we use the `-v` option so that we can count the number of lines that do **not** contain "murder". It turns out we can deduce that 7 lines contain the word "murder". This command can be useful in filtering out what we do not want.

##### Example 2: 
```
$ grep -v -e "murder" -e "blood" -e "police" -e "poison" -e "fire" technical/911report/*.txt | wc -l | sort
25422
```
* Now here is a stronger example. Suppose that I wanted lines that do not contain "murder", "blood", "police", "poison", or "fire". Then, I'd be able to use the `-e` option along with `-v` in order to make a stronger filter to give me what I want. In this case, we can see that there are 306 lines that contain either one or more of these words. Therefore, `-v` is a very powerful tool that can be used in combination with other commands to create a filter of what a user might not want in an output.

### -`w`
* Our good friend Chat-GPT describes this option as a way to match **whole words** as opposed to partial matches.
##### Example 1:
```
$ grep -w -l "gram" technical/biomed/*.txt
technical/biomed/1471-2121-4-1.txt
technical/biomed/1471-2148-1-4.txt
technical/biomed/1471-2148-1-8.txt
technical/biomed/1471-2180-2-22.txt
technical/biomed/1471-2180-2-35.txt
technical/biomed/1471-2180-2-7.txt
technical/biomed/1471-2180-3-10.txt
technical/biomed/1471-2180-3-15.txt
technical/biomed/1471-2180-3-4.txt
technical/biomed/1471-2180-3-5.txt
technical/biomed/1471-2202-2-20.txt
technical/biomed/1471-230X-2-23.txt
technical/biomed/1471-2334-1-13.txt
technical/biomed/1471-2369-3-1.txt
technical/biomed/1471-2458-2-11.txt
technical/biomed/1472-6785-2-6.txt
technical/biomed/1472-6904-1-2.txt
technical/biomed/1472-6904-2-7.txt
technical/biomed/1476-069X-2-7.txt
technical/biomed/1476-072X-2-4.txt
technical/biomed/1477-7827-1-27.txt
technical/biomed/1477-7827-1-43.txt
technical/biomed/ar104.txt
technical/biomed/gb-2003-4-6-r37.txt
```
* Here, I used the `-w` option to filter my search for **whole words** as opposed to partially.
* In this example, I used "gram" as a specific word in a scenario in which we want to find a measurement that we might remember to be in grams, but NOT something like kilograms.
* I also used the `-l` option in combination with `-w` to give me a list of the file names.
* Therefore, we can use the `-w` and `-l` options to give us a list of files that have exact matching words with what we want.

##### Example 2: (I added ... to make this page more readable)
```
$ grep -L -w "men" technical/government/Media/*.txt
technical/government/Media/5_Legal_Groups.txt
technical/government/Media/A_helping_hand.txt
technical/government/Media/A_Perk_of_Age.txt
.
.
.
technical/government/Media/Weak_economy.txt
technical/government/Media/Wilmington_lawyer.txt
technical/government/Media/Wingates_winds.txt
technical/government/Media/Working_for_Free.txt
```
* Here, I combined the `-L` option with the `-w` option to give me the files that did not contain "men".
* `-L` is new, and interestingly enough, I found it to be quite similar to the `-v` option from earlier, in which both print the opposite of what you want.
* In this scenario, suppose that a user wanted to search through the government/Media directory. They did not know which file they were looking for, but only knew that it did not contain men. Therefore, this combination of options will be of use as it will filter out men, while not excluding women.
* I think generally, `-w` is useful for pinpointing exact words or phrases, while not including partial matches.


### `-n`
* AI says that this option can be used in our grep search to show each matching line's **line number** in the file.




### -`m NUM`
* Chat-GPT describes this option as a way to tell grep to stop searching after a certain number of matches.



