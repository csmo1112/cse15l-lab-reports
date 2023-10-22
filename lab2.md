# Part 1
## Here's the code for `StringServer.java`:  
![image](https://github.com/csmo1112/cse15l-lab-reports/assets/147008706/dd3c1b0d-f073-4624-bc18-8b46133e699f)
![image](https://github.com/csmo1112/cse15l-lab-reports/assets/147008706/dbfa8993-277d-496c-beb7-4d000157e916)  
## And here are a few screenshots of `/add-message` running on my server:  
![image](https://github.com/csmo1112/cse15l-lab-reports/assets/147008706/abf45c2e-53e0-4c61-83b2-dd7705d7daed)  
The first test with a simple "hello" worked easily, but my main concern was storing the past messages to display after another message was written, so I searched [StackOverflow](https://stackoverflow.com/questions/13395114/how-to-initialize-liststring-object-in-java) to figure out how to make a string array and people suggested to use an ArrayList so that it can be indexed. I then used a `for` loop to run through the array and print out the messages stored in the string.
![image](https://github.com/csmo1112/cse15l-lab-reports/assets/147008706/e6a189b7-5637-429f-9e15-0629de76d296)  
For the cases with spaces, putting messages like "How are you" would be converted to `How+are+you` so I manually called a `string.replace('+',' ')` to address this case.

# Part 2  
Here is the path to my private key on my home computer:  
![image](https://github.com/csmo1112/cse15l-lab-reports/assets/147008706/7ff8ecbf-f9ec-47a7-9162-f3a1dc6247fb)  
Here is the path to my public key on `ieng6`:  
![image](https://github.com/csmo1112/cse15l-lab-reports/assets/147008706/4afc26c4-abfe-4e49-bc73-ad3f4eea994d)  
Here is the screenshot of logging into `ieng6` without a password:  
![image](https://github.com/csmo1112/cse15l-lab-reports/assets/147008706/64448e2b-d906-4599-9cd6-409879b1be9d)  

# Part 3
In weeks 2 and 3, I learned how to make a ssh connection to a server, and how to bypass the password on trusted devices. Unexpectedly, I also refreshed myself on Java to complete Part 1 of this assignment, and since my only experience with Java was AP CS A in high school, I learned how to use ArrayLists. 
