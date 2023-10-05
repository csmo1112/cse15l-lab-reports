cd with no arguments does not do anything because no directory is specified. 
ls with no arguments shows the available directory. In /home, it shows lecture1. 
cat with no arguments breaks the program, and need to do ctrl+z to exit

Here are the screenshots:
![](![Screenshot 2023-10-04 171934](https://github.com/csmo1112/cse15l-lab-reports/assets/147008706/21745c2c-b900-4eac-a0c2-84430829daa4)
)

cd with a directory (lecture1) changes the directory to lecture1. ls with the same directory shows the files and directories within lecture1, like the messages directory, Hello Java files, and the README. cat + directory shows this message:*cat: lecture1: Is a directory* 

Here are the screenshots:
![](![image](https://github.com/csmo1112/cse15l-lab-reports/assets/147008706/09557f91-865a-4453-a3c0-79f04e8fd3a7)
)

cd with a file throws an error that states: *bash: cd: README: Not a directory*. ls to a file gives the file. In my case, *ls en-us.txt* simply returned *en-us.txt* in the console. cat + file returns the contents of the file. In my case, *cat en-us.txt* returns *Hello World!*

Here are the screenshots:
![](![image](https://github.com/csmo1112/cse15l-lab-reports/assets/147008706/a1f1b680-085f-4531-a0c2-747075916b6e))
