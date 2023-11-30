# Debugging Scenario
## Ed Post
Hi, I am having trouble with lab 7, and I am running into an error. Here is the terminal output:  
![image](https://github.com/csmo1112/cse15l-lab-reports/assets/147008706/9339979b-4eb6-473c-b57c-d6d63d7ff8f0)  
and here is my code for the `merge()` function:  
![image](https://github.com/csmo1112/cse15l-lab-reports/assets/147008706/6866eb58-8601-4f5d-ad70-ed27853023f5)  
I was wondering why the first test case outputs something, while the other one has a memory error? Thanks.  

## Tutor's Response  
The memory error likely means that there is a memory leak in your program, which means that something is iterating and shouldn't be. Try looking at your loops and make sure everything is being iterated correctly. Also, the first error you are getting is in your `filter()` function, not the  `merge()` function. Take another look at it, and if you're still stuck, show me a screenshot of your code.  

## Student's Response  
Hi, thank you for your reply! I fixed the errors in `merge()`, but I still don't know how to pass the `filter()` test. Is there something where I can reverse the order of a list? Thanks.  
![image](https://github.com/csmo1112/cse15l-lab-reports/assets/147008706/beb760b6-46c6-4cf4-b040-4fdab00df4ca)  
![image](https://github.com/csmo1112/cse15l-lab-reports/assets/147008706/35559e5e-f07e-492e-b3c7-08b4e04e0300)  

## Tutor's Response  
I think there is an easier way to fix your code. Look at how your resulting array is changed each time a condition is fulfilled. What does `result.add(0, s)` do?  

## Student's Response  
Got it, I misread the question and thought I needed to put it in reverse order. I fixed it now, and all the tests pass. Thanks!  
![image](https://github.com/csmo1112/cse15l-lab-reports/assets/147008706/7dbfe65d-aaff-4504-a844-5e8b4cf85be8)    

# Reflection  
