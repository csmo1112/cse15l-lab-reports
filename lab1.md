## Functions with no argument  
**`cd` with no arguments** does not do anything because no directory is specified.  This does not throw an error.   
**`ls` with no arguments** shows the available directory. In `/home`, it shows `lecture1`. This does not throw an error.  
**`cat` with no arguments** returns a new line, and whatever following input you give will be returned until you type `ctrl+z` to exit. This is because `cat` expects a file as an argument, and without one it reads from the terminal and outputs what it is given. This does not throw an error.  

**Here are the screenshots:**  
![Screenshot 2023-10-04 171934](https://github.com/csmo1112/cse15l-lab-reports/assets/147008706/21745c2c-b900-4eac-a0c2-84430829daa4)\
![image](https://github.com/csmo1112/cse15l-lab-reports/assets/147008706/ce6112bb-0a74-4b00-99d1-85b5157f07e2)  


## Functions with a directory argument  
**`cd lecture1`** changes the directory to `lecture1` directory in `/home`. This does not throw an error.  
**`ls lecture1`** shows the files and directories within lecture1, like the `messages` directory, `Hello` Java files (`.class` and `.java` files), and the `README`.  This does not throw an error.    
**`cat lecture1`** shows this message: `cat: lecture1: Is a directory`. This does not throw an error, as it simply states that it is a directory.   

Here are the screenshots:  
![image](https://github.com/csmo1112/cse15l-lab-reports/assets/147008706/09557f91-865a-4453-a3c0-79f04e8fd3a7)  


## Functions with a file argument  
*To preface, this is in the directory `~/lecture1/messages`. To get here, type `cd lecture1` followed by `cd messages` or optionally, `cd lecture1/messages`.*  

**`cd en-us.txt`** throws an error that states: `bash: cd: en-us: Not a directory`.  
**`ls en-us.txt`** gives the file. In my case, `ls en-us.txt` simply returned `en-us.txt` in the console. This does not throw an error.   
**`cat en-us.txt`** returns the contents of the file. In my case, `cat en-us.txt` returns `Hello World!`. This does not throw an error.     

Here are the screenshots:  
![image](https://github.com/csmo1112/cse15l-lab-reports/assets/147008706/a1f1b680-085f-4531-a0c2-747075916b6e)
