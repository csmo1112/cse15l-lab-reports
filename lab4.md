## Step 4: logging into ieng6:  
I typed `ssh cs15lfa23sl@ieng6.ucsd.edu <enter>` and was prompted a password because I was logging in from another lab computer, and got this this in the terminal:  
![image](https://github.com/csmo1112/cse15l-lab-reports/assets/147008706/76fa66a4-8c29-4b72-86b9-7a7a240f8420)  

## Step 5: cloning the repo using `.ssh` URL  
In the command line, I wrote `git clone git@github.com:csmo1112/lab7.git <enter>` and got:  
![image](https://github.com/csmo1112/cse15l-lab-reports/assets/147008706/ccf2aaad-4586-4160-aef1-d7999e191c8a)  

## Step 6: running tests and showing that they fail  
To test, I typed `bash test.sh <enter>` and as expected, the tests failed:  
![image](https://github.com/csmo1112/cse15l-lab-reports/assets/147008706/c7077379-7c8b-49c0-a4fa-46f42ad0fc53)  

## Step 7: editing the code to fix the failing test  
I began by typing `vim ListExamples.java <enter>` to open the file, then pressed 'j` 43 times to get to the line I needed to change, then typed `l` 11 times to have the cursor over the 1 in `index1` and typed `r2` to replace 1 with 2.  
![image](https://github.com/csmo1112/cse15l-lab-reports/assets/147008706/7b78dd8b-27da-41db-b323-f9d2c263a68c)  
I then typed `:wq <enter>` to save and exit vim.  

## Step 8: run tests and make sure the tests pass  
Typing `bash test.sh <enter>` just like in step 6, I get this message in the terminal, showing that the test now passed:  
![image](https://github.com/csmo1112/cse15l-lab-reports/assets/147008706/c64d1a4d-fe48-44cb-8243-816fed24840b)

## Step 9: committing and pushing the file  
After I made sure the tests passed, I typed `git add ListExamples.java` followed by `git commit -m "update ListExamples.java"` and finally `git push` to push my changes into my GitHub repository.  
![image](https://github.com/csmo1112/cse15l-lab-reports/assets/147008706/a3941a7c-60bc-4a8c-b319-3b375b63b725)  
As you can see, it states that there was 1 file changed, 1 insertion, and 1 deletion corresponding to changing the variable name from `index1` to `index2`.
