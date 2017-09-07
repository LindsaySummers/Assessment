### August 2017

![AssessmentQuestions]  
  
----------
# BEFORE
### ★ Added New Column with Formula:
>***=MID(D7,5,1)***  
>Returns exact the last character of the 5-digit zip code string (and if the zip code does not have 5 characters, then it returns nothing – which is good to double check any errors as to why there is not a 5-digit zip code)  
  
### ★ “Froze” the Top Six Panes  
>I froze them so that data can sort without sorting the column headers.  
>Sorted this new column of last digits, 0-9, and then non-numbers at the bottom.  
  
### ★ Filtered and Deleted 3's, 5's, and 7's
>Filtered the data by new column so that only “3” entries showed – then deleted all.  
>Repeated filtering and deleting for 5 and 7 as well.  
  
### ★ Added Another New Column with Formula:  
>***=ISNUMBER(SEARCH("foreign",F7))***  
>This checks to see which schools are “foreign” institutions.  
  
----------
# QUESTION 1 (*ANSWER=1*)  
  
### ★ New Columns and Formula:  
>***=IF(ISNUMBER(SEARCH("-",O7))=TRUE,0,O7)***
>The formula checked the column next to it (“$ of Disbursements”) to see if there is a “-“ which denotes no money, and returns a “0” (zero) instead. If there are only numbers in the cell, and no “-” (which denotes any money value), then it returns that money value. I did this only to correct the dash “-“ into a numeric value in order to use it in an addition formula.  
>I did this 6 times for the 2010-2011 data and for the 2015-2016 data (at the same time, by highlight both worksheets at once), in order to derive the sum of $ disbursements.  
  
### ★ Is the Sum Between $2000-$9500?  
>***=IF(AND(I7>=2000,I7<9500),"yes","no")***  
>Once I had the sum, I then used a conditional statement to determine if the sum fell between $2000 (or equal to) and $9500, with a simple “yes” or “no”  
  
### ★ Count How Many Between
>***=COUNTIF(H7:H3520,"yes")***  
>Now that I have “answers,” I simply counted all the “yes”-answers  
>I did this both both sets of data at the same time.  

### ★ Time to Compare!
>Once I had two numerical answers, I simply subtracted since the question was “how many MORE…?”  
>153-152 = 1  
  
----------
# QUESTION 2 (*ANSWER= 2*)
I used a similar method from Question 1:  
  
### ★ Added New Column and Formula
>***=IF(ISNUMBER(SEARCH("-",W64))=TRUE,0,W64)***  
>I inserted new columns next to all the columns named “$ of Loans Originated” and used the same formula from Question 1 in order to convert all the dashes into zeros (to easily find the sums).  
  
### ★ Addition  
>***=V64+AC64+AJ64+AQ64+AX64***  
>Then, I added all the new “$ of Loans Originated” per school.  
  
### ★ Which Are More Than $20-Million?  
>***=IF(Q64>20000000,"yes","no")***  
>Next, in another new column, a formula to identify which schools had a sum of more than $20,000,000 (with a simple “yes” or “no”).
  
### ★ How Many? Let's Count!
>***=COUNTIF(P7:P3520,"yes")***  
>Finally, in one of the cells in the top “frozen” rows, a formula to count all the “yes” answers.  
>I did this for both 2010 and 2015 sheets at the same time.  
  
### ★ Time to Compare!
>Now to compare both answers (since the question was "how many MORE...?"
>2015 had 530 schools with over $20-million in loans (if they were fully disbursed)
>2010 had 528 schools with over $20-million in loans (if they were fully disbursed)
>530-528 = 2


  
  

[AssessmentQuestions]: https://
