## Feedback 

Nice work on this project, you can consider it complete. I'm going to read your files in order and give you feedback
as I move through them, from Task 1 to Task 3. 

I'm not sure `Python.gitignore` will work to have files ignored. In my experience the name of the file *has* to be exactly `.gitignore`. 

Looking at your `submission.md`, it appears that something has gone wrong. It's not neccessary to fix it, but I'd like to you do the work to figure out what it is. I'd recommend calculating the number of rows per month from 2010-01-01 through 2017-01-31. Do this on your data and on mine and plot them. Is it obvious what's gone wrong? (We can tell it's no 2014 based on some of the other queries. 

### Task 1

* You've written this code in a _very_ general way. For instance, lines like this are useful if you're writing generic DE code: `for root, _, files in os.walk(destination_folder):`. But we're not in such a generic world. I'd encourage you to strike a balance that's a bit more bespoke. It's okay to know where on your computer the data is and have the files sitting in a folder you control. 

You don't need to do 
```
if __name__ == "__main__": # trick from Claude again
    main()
```
in a notebook. This is only used in .py files if you want to import them as modules or call them from the command line. 

Otherwise this looks good and _extremely_ thorough. 

### Task 2

* Nice job on this task. 
* It'd be worth thinking through how you'd do this the reproducible way. That'd involve selecting distinct card numbers, pulling them down to python, calling `random.sample` and then building a query that could use them all. Let me know if it's not clear how you'd do that. 


### Task 3

* Nice job on this, very efficient. 
* And unlike the vast majority of your classmates, your query is pretty spot on. (I exclude departments 0 and 15 in "Intro to SQL" and in my solution. 

