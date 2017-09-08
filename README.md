### August 2017

![AssessmentQuestions]  
  
----------
# SET UP BEFORE
*Please note, that when I "insert column with formula" and give the example, that example is just for the first cell in the column.  
Then, I double click on the bottom right corner of the highlighted cell with formula so that the formula continues for the entire column. To streamline directions, I will not write this out every time*  
  
### ★ New Workbook & Two New Spreadsheets  
>First, I opened a new, separate, Excel file with two spreadsheets - one for each set of the data sets (2010, and the other for 2015)  
  
### ★ Copy, Paste, Rename, Repeat 
>(Copy) I copied the 2010 data (by clicking on the top left corner, it highlights ALL data)  
>(Paste) I pasted that data into the new workbook  
>(Rename) I renamed the current worksheet to "2010"  
>(Repeat) I repeated these steps exactly for the 2015 data
  
### ★ “Freeze” the Top Six Panes  
>***VIEW >> FREEZE PANES***  
>By clicking on A7 - The first column, so that no columns before are affected, and the 7th row, so that the first 6 rows "Freeze"  
>I froze them so that data can sort without sorting the column headers.  
>Sorted this new column of last digits, 0-9, and then non-numbers at the bottom.  
>Repeat steps for both spreadsheets  
  
### ★ Insert Column with Formula
>***=MID(D7,5,1)***  
>Returns exactly the last character of the 5-digit zip code string (and if the zip code does not have 5 characters, then it returns nothing – which is good to double check any errors as to why there is not a 5-digit zip code)  
>(continued for entire column, as the note applies above)
  
### ★ Filter & Delete 3's, 5's, and 7's
>Highlight row 6 (since those are the header titles to our columns)
>***DATA >> FILTER***   
>Now each column can be Filtered (good for later use)
>Filtered the data in the new column so that only “3” entries showed  
>Then, deleted all rows with "3" entries  
>Repeated filtering and deleting rows for 5s and 7s as well.  
>**NOTE:** Click on the first row, and then to highlight all row quickly (instead of scrolling down), CTRL+SHIFT+DownArrow  
>**NOTE:** To make sure all 3's (for example) were deleted, you should NOT see "3" as a choice in your Filter-Menu from now on.   
  
### ★ Insert Another Column with Formula  
>(Next to the "School Type" Column)  
>***=ISNUMBER(SEARCH("foreign",F7))***  
>This checks to see which schools are “foreign” institutions and will return a simple "TRUE" or "FALSE".  
  
### ★ Filter & Delete Foreign Institutions  
>Filter this new column so that you see only "TRUE" (which means, "yes, it is TRUE that this is a foreign institution")  
>Delete all rows with "TRUE"  
  
**NOTE:** Repeat all of these steps again for other data set as well!  
  
----------
### QUESTION 1: Consider all of the schools that disbursed a total of greater than or equal to $2,000 and less than $9,500 in loans for the time period reported on the spreadsheets provided (i.e. quarter 1). How many more schools met this criteria in 2015 than in 2010?  
  
# *ANSWER=1*  
  
***NOTE:** Before beginning, hold down CTRL and click on the other tab (the other spreadsheet of the other data set). This will highlight BOTH tab so that you can work with both data sets at once and save you half the amount of time.  
If you're wondering why I didn't do this before, it's because entries were being deleted... So to be on the save side, I thought it was best to work with each data set separately.  
HOWEVER, now that we're not deleting, AND both worksheets are set up with the exact same columns, we most certainly can use this shortcut!*  
  
### ★ Insert Columns with Formula  
>(Next to ALL the "$ of Disbursements" Columns for each type of loan:  
>Note, that there are 6:  
>(1) DL SUBSIDIZED- UNDERGRADUATE  
>(2) DL SUBSIDIZED- GRADUATE  
>(3) DL UNSUBSIDIZED- UNDERGRADUATE  
>(4) DL UNSUBSIDIZED- GRADUATE  
>(5) DL PARENT PLUS  
>(6) DL GRAD PLUS 
>  
>In the newly added columns, this formula:  
>***=IF(ISNUMBER(SEARCH("-",O7))=TRUE,0,O7)***  
>The formula checks the column next to it (“$ of Disbursements”) to see if there is a “-“ which denotes no money, and returns a “0” (zero) instead. If there are only numbers in the cell, and no “-” (which denotes any money value), then it returns that money value. I did this only to correct the dash “-“ into a numeric value in order to use it in an addition formula.  
>  
>I did this 6 times for the 2010-2011 data and for the 2015-2016 data (at the same time, by highlight both worksheets at once), in order to derive the sum of $ disbursements.  
  
### ★ Is the Sum Between $2000-$9500?  
>Insert another column on the left side of the all the loans with formula:  
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
>  
>**NOTE:** I originally had the thought to use a "LOOKUP"-formula to quickly identify the schools automatically. However, that plan didn't work for two reasons:  
>(1) because "=VLOOKUP"-formula has to match EXACTLY; so if I typed "and" instead of "&", the formula wouldn't work  
>(2) because if I tried to identify just key words instead of being exact, then the satellite schools would also be included, which also would not work.  
>  
>Hence, since there were only 7 schools, the easiest, and quickest, way for me to accomplish this task was to filter by state and manually make a note  
  
### ★ Filter Only Colonial Schools  
> It's way easier to work with just the 7 schools instead of all the data!  
  
### ★ Insert Columns with Formulas (Optional)  
> I quickly added two columns:  
>(1) # of Recipients of DL Gradeuate, and  
>(2) # of Recipients of DLGrad Plus loans  
>which really just copied the columns of data to where I was working  
>  
>**NOTE:** This was NOT necessary, but I just like to see the data side-by-side to where I'm currently working  

### ★ Add Both for Total Recipients
>***=G457+H457***  
>DL Gradeuate or (plus) DLGrad Plus loans  
>I then inserted another column to add both of the previously mentioned recipients for each school.  
>  
>**NOTE:** I added because "OR" means either could work to accomplish the task. For example, if I rolled a die and I win the game if I roll a 3 OR 5. Then you would ADD the probabilites together... Or think about a Venn Diagram: BOTH of the overlapping circles would be shaded in.  
  
### ★ Rutgers "Wins"!
>5488 (DL Gradeuate Loans) + 1374 (DLGrad Plus Loans)  
>=6,862

----------
# QUESTION 4 (*ANSWER= 5889721*)
***$5,889,721, from City University of Seattle, was the median value of fully disbursed unsubsidized graduate loans.***  
  
### ★ Research List of Info'
>First, I searched for a list of the zip codes of King County.  
>I found a list which was already in a chart, which made it super easy to insert into a spreadsheet - PERFECT!  
  
### ★ New Data, New Sheet!  
>I inserted a new sheet, copy-and-pasted the data set (all the zip codes in King County).  
  
### ★ Filter the Data!  
>If we're only looking for King County Schools, let's filter out ALL the states except for WA!  
  
### ★ Insert Column and Formula  
>***=VLOOKUP(L296,'King County'!$A$2:$C$153,3,FALSE)***  
>NOW I can use a fast and convenient "LOOKUP" formula (Yay! So easy! Remember the one I was thinking of in Question 3 but it would have been more trouble than it was worth?)  
>This formula basically says "Grab the zipcode that was given in the original data set and try to match it to the new zip code chart (on the other sheet). IF there is a match, then write "King County"  
>(which is what that "3" is in the formula... the third column of my newly inserted chart was entirely "King County")  
>  
>**NOTE:** This is kind of like the "COUNT" formulas I used before in the sense of just findind "Answers" quickly.  
>  
>I could have had that third column say "Yes", or "Lindsay is Awesome", or "Ada Rocks".... It really doesn't matter - it's just a quick bookmark to mark which entries I want to look at.  
  
### ★ Filter the Data (Again)!  
>Now that we've identified all of the King County schools, let's filter the data so that only those schools are showing.  
>Six King County schools are shown  

### ★ Insert Column and Formula  
>***=AJ296***  
>This is just a quick way to pull the one column of data that we want: "Direct Loans Unsubsidized Graduate, $ of Loans Originated"  
  
### ★ Sort: Smallest to Largest  
>In this newly added column of six entries, 5 were non-zero entries.  
>We need to sort the data (doesn't matter in which direction, but I sorted from smallest to largest)  
  
### ★ Indentify the Median  
> The median is the number in the middle of sorted data. In this case, there were 2 less than it, and two greater than it (since there were 5 non-zero entries).  
>Therefore, the median number is 5889721
  
----------
# QUESTION 5 (*ANSWER= 193850316*)
***$193,850,316 is the sum of all fully disbursed Grad Plus loans within 2015-2016 from the football-champion-schools from 2001-2015 (inclusive).***  

### ★ Research First!
>I referred to www.ncaa.com in order to obtain the information about which schools were football champions.  
>The information I found on that website was helpful, but also a bit vague, so I crossed refereced this information with other online sources. I did this in order to confirm the school names (Example: “Florida” is indeed the “University of Florida” and not “Florida University”).  
>  
>**NOTE:** I put this information in a list on a separate sheet  
  
### ★ Another Column for Football Champs  
>Once I had a list (in another sheet) of all the football champs, I added another column to make a note on the main data list of which schools these were...  
>I did this manually for the same reason as in Question 3 ("LOOKUP" formulas just weren't a good option, and there weren't that many to quickly filter and make a quick note.  
  
### ★ Insert Column and Formula  
>***=AX1125***  
>Just like all the times before, all I did was, simply, insert a new column and use a formula to copy the "Fully Disbursed for Grad Plus, $ of Loans Originated" so that the important information was all together in a nice location where I was working...  
>I "pulled" this formula down for the other 5 entries in the column.
  
### ★ Addition  
>***=SUM(C7:C10000)***  
>Now that we have 6 entries with a dollar amount, we need to simply add the six entries.
>So, finally, in one of the cells in the top “frozen” rows, a formula to find the sum.
>The result is "193850316"



[AssessmentQuestions]: https://github.com/LindsaySummers/Assessment/blob/master/Assessment%20Questions.png
