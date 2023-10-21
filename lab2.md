# Part 1
## Here's the code for `StringServer.java`:  
![image](https://github.com/csmo1112/cse15l-lab-reports/assets/147008706/dd3c1b0d-f073-4624-bc18-8b46133e699f)
![image](https://github.com/csmo1112/cse15l-lab-reports/assets/147008706/dbfa8993-277d-496c-beb7-4d000157e916)  

## And here are a few screenshots of `/add-message` running on my server:  
![image](https://github.com/csmo1112/cse15l-lab-reports/assets/147008706/abf45c2e-53e0-4c61-83b2-dd7705d7daed)  
The first test with a simple "hello" worked easily, but my main concern was storing the past messages to display after another message was written, so I searched (StackOverflow)[https://stackoverflow.com/questions/13395114/how-to-initialize-liststring-object-in-java] to figure out how to make a string array and people suggested to use an ArrayList so that it can be indexed. I then used a `for` loop to run through the array and print out the messages stored in the string.
![image](https://github.com/csmo1112/cse15l-lab-reports/assets/147008706/e6a189b7-5637-429f-9e15-0629de76d296)  
For the cases with spaces, putting messages like "How are you" would be converted to `How+are+you` so I manually called a `string.replace('+',' ')` to address this case.
