### August 2017

![AssessmentQuestions]  
  
----------
# BEFORE
### ★ Insert Column with Formula
>***=MID(D7,5,1)***  
>Returns exact the last character of the 5-digit zip code string (and if the zip code does not have 5 characters, then it returns nothing – which is good to double check any errors as to why there is not a 5-digit zip code)  
  
### ★ “Froze” the Top Six Panes  
>I froze them so that data can sort without sorting the column headers.  
>Sorted this new column of last digits, 0-9, and then non-numbers at the bottom.  
  
### ★ Filtered and Deleted 3's, 5's, and 7's
>Filtered the data by new column so that only “3” entries showed – then deleted all.  
>Repeated filtering and deleting for 5 and 7 as well.  
  
### ★ Insert Another Column with Formula  
>***=ISNUMBER(SEARCH("foreign",F7))***  
>This checks to see which schools are “foreign” institutions.  
  
----------
# QUESTION 1 (*ANSWER=1*)  
  
### ★ Insert Column with Formula  
>***=IF(ISNUMBER(SEARCH("-",O7))=TRUE,0,O7)***  
>The formula checked the column next to it (“$ of Disbursements”) to see if there is a “-“ which denotes no money, and returns a “0” (zero) instead. If there are only numbers in the cell, and no “-” (which denotes any money value), then it returns that money value. I did this only to correct the dash “-“ into a numeric value in order to use it in an addition formula.  
>I did this 6 times for the 2010-2011 data and for the 2015-2016 data (at the same time, by highlight both worksheets at once), in order to derive the sum of $ disbursements.  
  
### ★ Is the Sum Between $2000-$9500?  
>***=IF(AND(I7>=2000,I7<9500),"yes","no")***  
>Once I had the sum, I then used a conditional statement to determine if the sum fell between $2000 (or equal to) and $9500, with a simple “yes” or “no”  
  
### ★ How Many? Let's Count!  
>***=COUNTIF(H7:H3520,"yes")***  
>Now that I have “answers,” I simply counted all the “yes”-answers  
>I did this both both sets of data at the same time.  

### ★ Time to Compare!
>Once I had two numerical answers, I simply subtracted since the question was “how many MORE…?”  
>153-152 = 1  
  
----------
# QUESTION 2 (*ANSWER= 2*)  
I used a similar method from Question 1:  
  
### ★ Insert Column with Formula  
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
  
----------
# QUESTION 3 (*ANSWER= 6862*)  
***In 2015, Rutgers University had the largest number of recipients (6,862) who received either the DL Graduate or DL Grad Plus loans.***  
  
### ★ Colonial Colleges?  
>First, I had to look up which schools were colonial colleges which were founded before the declaration of independence.  
  
### ★ Another Column for Colonial Notes  
>Once I had the list of the 9 colonial schools, I inserted another column just so I could make a note of these schools (which turned out to only be 7, because two were eliminated due to their zip codes).  
>I filtered by state and manually found the school alphabetically because...  
>NOTE: I originally had the thought to use a "LOOKUP"-formula to quickly identify the schools automatically. However, that plan didn't work for two reasons:  
>(1) because "=VLOOKUP"-formula has to match EXACTLY; so if I typed "and" instead of "&", the formula wouldn't work  
>(2) because if I tried to identify just key words instead of being exact, then the satellite schools would also be included, which also would not work.  
>Hence, since there were only 7 schools, the easiest, and quickest, way for me to accomplish this task was to filter by state and manually make a note  
  
### ★ Filter Only Colonial Schools  
> It's way easier to work with just the 7 schools instead of all the data!  
  
### ★ Insert Columns with Formulas (Optional)  
> I quickly added two columns:  
>(1) # of Recipients of DL Gradeuate, and  
>(2) # of Recipients of DLGrad Plus loans  
>which was just copying the columns of data to where I was working  
>NOTE: This was necessary, but I just like to see the data side-by-side to where I'm currently working  

### ★ Add Both for Total Recipients
>***=G457+H457***  
>DL Gradeuate or (plus) DLGrad Plus loans  
>I then inserted another column to add both of the previously mentioned recipients for each school.  
>NOTE: I added because "OR" means either could work to accomplish the task. For example, if I rolled a die and I win the game if I roll a 3 OR 5. Then you would ADD the probabilites together... Or think about a Venn Diagram: BOTH of the overlapping circles would be shaded in.  
  
### ★ Rutgers "Wins"!
>5488 (DL Gradeuate Loans) + 1374 (DLGrad Plus Loans)  
>=6,862

----------
# QUESTION 4 (*ANSWER= 5889721)
***$5,889,721, from City University of Seattle, was the median value of fully disbursed unsubsidized graduate loans.***

  

[AssessmentQuestions]: https://
