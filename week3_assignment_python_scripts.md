# Objective

In this assignment, you will write a Python script that will sort numbers of a list.

It is based in what we did in class. You should modify the [sorting.py](https://canvas.newschool.edu/files/125691746/download?download_frd=1) script until you get the correct result.

### Running the python script

1. You can run it in the command line. For that, you need to Download the **sorting.py** file and move it to your course directory.

   In my case, that is `~/Coala/` (remember that the **~** stands for "home").

2. I suggest creating a backup copy of the original file with a different name, so you can always check how it was before you made changes to it. I will name my copy **sorting.py.bak** (bak standing for backup).

3. Open your terminal and go to your course directory. Remember to use `cd` to change directory, and `ls` to see what's in the directory. If you're ever lost, `pwd` will tell you where you are, and `cd ~` will bring you back to your home directory.

```bash
cd Coala
ls
```

    If you see **sorting.py** in the output, it means you are ready to run it.

4. Run it with the **Python** command. This is the syntax:
`Python file_name`

   For example:  
   `Python sorting.py`

   If everything is correct, you should see this in the beginning of the output:

       > "Good job! You have correctly been able to run this python script..."

Now you need to change the contents of the **sorting.py** file to make the sort operation work.

## Editing the script

1. Opening the file on VSCode

    To edit the script, you need to use a Text Editor. In our case, we are using **VSCode**. Since you are in the terminal, try opening it from there with the `code` command, it is the most convenient way:

	The general syntax is `code file_name`. In our case here:

	```bash
	code sorting.py
	```

This should open the **sorting.py** file in your VSCode.

If you get an error message, this just means your VSCode is not "connected" to the terminal yet. Remind me in class because this is an easy fix. If you wanna try it by yourself [check this quick guide](https://code.visualstudio.com/docs/setup/mac#:~:text=Keep%20in%20Dock.-,Launching%20from%20the%20command%20line,code'%20command%20in%20PATH%20command.)

Alternatively, you can open VSCode normally (through **Finder** or Start Menu) and open the **sorting.py** file. Make sure you navigate your folder structure to the course's folder, where **sorting.py** is.

## Understanding the script

Now that you have the file open, take a good look at it before making any changes.

Can you notice how some lines have a single color? What do they have in common?

These lines are called **comments**. They are meant to be a way for us to write notes for us humans to read, which will be ignored by the Python interpreter. If you want to write a comment, just add a **#** in the beginning of a line. The Python interpreter will just skip to the next line looking for the next instruction.

Notice that I've used **comments** to send *you* some messages. I'm telling you not to change anything above a certain line and not change anything below some other line. In sum, all changes you'll do to this script will be in the middle between the "#####" lines.

Don't expect to understand all the code in the beginning and end of the file (the code you should **not** change), because we haven't covered all of it.

Just so you know what's going on:

- In the first lines, I'm setting the script so you can work on it. I'm importing libraries that I'll need (more on that in a future class). I'm creating a random list of a thousand numbers ranging from 0 to 10000 and calling it **unsorted_list**. This is the list you will sort. You may remember in class that we sorted a list by finding the current smallest value of the unsorted list and adding it to the end of the sorted list.

- I've created **sorted_list** which starts as an empty list.
Python doesn't come with an "infinity" number by default, so I had to import the **math** module, and stored that value in a variable called **infinity** which now you may use. I've even created the **smallest** value and assigned it to infinity, so you can see how it's done. Remember that **you'll need do this operation again somewhere inside the script** for it to work.

- To check if your script got to the correct solution, which involves the **solution** variable. **You are not supposed to mess with it at all.**

- Finally I've added some printing commands to output in the terminal when you run the script. If you did everything right, you should see the sentence: "Congratulations! You have correctly sorted the list!"

## Editing the script

1. Making changes to the script and running it again

	- Anytime you make changes, you need to save the file before running again from the terminal.
	- Make sure you have created a backup copy of your file like I suggested above. If you have, you can now start making changes to the file.

1. First edit: a comment

	Start by trying to add a comment.

	- Pick a random line and add a **#** and some text after it. Something like `# This is my first comment. Yay!`
	- Now save the file.
	- Go back to the terminal and run the script again with `python sorting.py`

	If you didn't get an error message, that's great! Your comment should not change anything in the script, so you should get the same output as before

1. Second edit: a **print** command

	- Add a line with a print command, so you can see it in the terminal's output.
	- It can be something like:
      ```python
      print("I know how to print stuff!")
      ```
	- Make sure that whatever is inside the parenthesis is between quotes.
	- Save the file and run.

	If this sentence is showing up in the terminal output, you're on the right track!\
	Now you can delete this sentence, since it will not be useful for the assignment. Save the file again.

## Creating your own script

Now it's the time to put all into practice. There will be errors. That's just the nature of it. Try not to stress over it. I'll be there to help you in class.

Some tips:
- Try to test step by step of your script. 
- Don't try to write it all, because when the error message comes, you'll have no idea where it is. 
- Run it part by part and you will know exactly where the problem is.


### Tools

1. **Variables**

	To store or to update the value of a variable, you will use the **assignment** operator (`=`) in the following format:

	**variable_name = value (or expression)**

  	Examples:

    ```python
    my_age = 16
    greeting = "Hello world!"
    average_grade = (grade_a + grade_b + grade_c) / 3
    ```

    Notice a few things:

    - There can be no spaces in the variable name. Only regular characters, numbers and underscore (`_`)
    - You can't start a variable name with a number. `2student` is *not* a valid variable name, but `student2` is.

2. **Checking if a list is empty**

    In python there is the function **len()** that will tell the lenght of whatever is inside the parenthesys.

    For example, if you have these three lists:

    ```python
    list_a = [2, 4, 7]
    list_b = []
    list_c = ["apple", "banana"]
    ```

    `len(list_a)` will be equal to 3; `len(list_b)` will be equal to 0; and `len(list_c)` will be equal to 2.

    In sum, checking if a list is empty is the same as *checking if the length of a list equals 0*.

    To check for any kind of equality, we use the **equal to** operator (`==`). Don't confuse it with the **assignment** operator (`=`).

    The following statements,

    ```python
    len(list_a) == 0
    len(list_b) == 0
    len(list_c) == 0
    ```
     would output **False**, **True**, and **False** respectively.

3. **Running a sequence of operations *while* a certain condition is met**

    The **while loop** allows us to repeat any number of operations in a loop for as long as the condition we set remains true.

    The while loop has the following format:

    ```
    while some_condition:
        do_something
        do_another_thing
        do_yet_another_thing
    ```

    It is very important that all the operations are **exactly** 4 spaces to the right of the while loop. Python is very strict about spacing.

    An example of a while loop:

    ```python
    number = 5
    while number > 0:
        print(number)
        number = number - 1
    ```

    And the output will be:
    ```
    5
    4
    3
    2
    1
    ```

    Attention: be careful when creating a while loop. You need to make sure your condition will eventually be met, otherwise you will be stuck in an infinite loop. If that happens, press **Ctrl-c** (not Command-c) to quit the script and go back to fix your loop.

    Example of an infinite loop:

    ```python
    number = 4
    while number < 10:
        print(number)
        number = number - 1
    ```

    If you run the above, your terminal will be printing smaller and smaller numbers forever (or for a very long time)

4. **Compare values**

    You can use the operators to compare values:
    | Character  | Meaning |
    | ------------- | ------------- |
    | **>** |	greater than |
    | **<** | smaller than |
    | **>=** | greater than or equals to|
    | **<=** | smaller than or equals to|
    | **==** | equals to |

    For example,

    ```python
    4 > 5
    33 == 22
    101 > -23
    4 > 4
    4 >= 4
    ```

    will output to **False**, **False**, **True**, **False**, **True**, respectively.

5. **Loop to do things item by item of a list (*for loop*)**

    The **for loop** is one of the most used tools in python programming. It has a somewhat unintuitive syntax, but once you use it many times, it will become second nature to you.

    ```
    for place_holder_name in list_name:
        action_a
        action_b
        action_c
    ```

    Once again, it is crucial that all the actions that "belong" to the **for loop** are 4 spaces to the right of it.

    The **for loop** will do a few things automatically. For every loop, it will:

    - assign **place_holder_name** (whatever name you decide to put there) to the next value in **list_name**, starting from first all the way to the last.
    - run operations in sequence, from first to last (**action_a**, **action_b**, **action_c**...)
    - when the for loop assigns **place_holder_name** to the last item in **list_name**, it will run the operations for the last time, then the loop will be over.

    For example,

    ```python
    id_age = [17, 21, 43, 15]

    for age in id_age:
        if age >= 21:
            print("You are old enought to drink")
    ```

    In this case, the loop will assign **age** to each of the items, one at a time and run the operation that will check if the age is greater or equal than 21. If it is, it will print "You are old enought to drink". Notice that the **print** line is 4 spaces after the **if** line, because it "belongs" to it. It means it will only print when the condition of the **if** line is met. Otherwise, if the **if** condition isn't met, the program will just skip the **print** line and move to the next loop of the **for loop**.

6. **Append value to the end of a list**

    You can append a value using the **.append()** method. Whatever value or expression you put inside the parenthesys will be appended to the end of list that comes before the **.append()** method.

    The general syntax is: `list_name.append(value)`

    For example:

    ```python
    my_list = [4, 2]
    new_number = 7

    my_list.append(5)
    my_list.append(new_number)
    ```

    The final value of **my_list** will be **[4, 2, 7, 5]

7. **Remove value from list**

    The **.remove()** method removes the first matching element from a list. *The first match* of the value or expression you put inside the parenthesys will be removed from the list that came with the **.remove()** method.

    The general syntax is: `list_name.remove(value)`

    For example:

    ```python
    my_list = [5, 1, 9, 4, 1, 5, 3, 7]
    bad_number = 5

    my_list.remove(1)
    my_list.remove(bad_number)
    my_list.remove(5)
    my_list.remove(7)
    ```

    The final value of **my_list** should be **[9, 4, 1, 3]**.
