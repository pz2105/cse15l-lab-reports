# Comparison of Two Implementation on Two Chosen Test Files
[My MarkdownParse Repo](https://github.com/pz2105/myMarkdownParse.git)   
[Reviewed MarkdownPrase Repo](https://github.com/ucsd-cse15l-w22/markdown-parse.git)
## How I Found The Tests
-First I added a line to the bash scipt so that before printing out each result from the `test-files`, it would gives the name of the test file we are running our program on
![Image](lab5-s1-1.png)     
-Then, I ran the test folder on provided java file and export the result to `public-results.txt`.
![Image](lab5-s1-2.png)     
-Next, I imported the `MarkdownParse.java` file our group was working on and perform the same thing above, exporting the result to `own-results.txt`.
![Image](lab5-s1-3.png)     
![Image](lab5-s1-4.png)     
![Image](lab5-s1-5.png)     
In order the compare the two files, I used the command `diff` followed by the two files I just created. Searching within the output, I am able to locate the file the program was running on since I added the file name up front (order of accessing the file within folder does not following numerical order).
![Image](lab5-s1-6.png)     



## First Test
![Image](lab5-s2-1.png)  
![Image](lab5-s2-2.png)  
-For file `577.md`, the output with our own implementation is `[]`, while that for provided implementation is `[train.jpg]`.  
-Since this is an image, the actual result should be `[]`. Thus, the implementation provided is incorrect.
![Image](lab5-s2-3.png)  
![Image](lab5-s2-4.png)  
-As we can see, the provided java file did not take image into account, which is indicated by `!` that comes before `[`. In order to make this implementation behave correctly, we should add an if statement on each `[` to identify a potential image.



## Second Test
![Image](lab5-s3-1.png)  
-For file `509.md`, the output with our own implementation is `[    /uri \n "title"]`, while that for provided implementation is `[]`. Since no link should contain space or `\n`, the actual output should be `[]`.
![Image](lab5-s2-3.png)  
![Image](lab5-s2-4.png)  
-The implementation provided takes into account that if there is space or `\n` envolved inside within a potential link, it should not be considered a valid link. However, within the our own implementation, the program simply search for next close `]`, without taking care of space or `\n`, which is incorrect. Thus, in order to fix it, we ought to check `\n` as well as space just like the provided implementation.