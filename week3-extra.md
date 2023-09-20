# Extra Assignment

To practice your new skills in Python loops and conditionals, try this harder assignment

1) Write a script from scratch.
    You can, of course, take a look at your other script for hints on how to do things. I encourage you *not* to copy it, because it can make it more confusing for yourself. Not everything that is there will be useful here, and some things will even make the new script not work properly.
    Think about what you want to do, and check what parts of the old script will be repeated in the new script, what parts will not, and what else will still need to be done.
2) Your new script should check a list of numbers and will print a final list with modifications to these numbers. These are the modifications:
   1) If the number is zero or negative, the final list should not show it at all.
   2) If the number is odd:
      1) If the number is divisible by 3, the final list should have the result of the number divided by 3
      2) If the number is divisible by 5, the final list should have the number unmodified.
      3) If the number is odd, is not divisible by 3, and is not divisible by 5, don't send it to the final list.
   1) If the number is even, the final list should have the result of that number divided by 2
   1) All discarded numbers should go to a `discarded_list`.
3) The final list, should have numbers in descending order.
   You can do that in two ways:
     1) **First Option**: modifying the while loop of your previous script.\
        In this route, make sure you have these two lines:
        ```python
        import math
        negative_infinity = -math.inf
        ```
        The first line is exactly how it was in the previous script. We need the **math** library to be able to use infinity, since python doesn't come with it by default. The important change is that in the previous script we used "regular" (positive) infinity, but this time you'll need negative infinity. Why? Think about the operations you want do to sort in the descending order.
        Once you add these two lines, you can use `negative_infinity` as a value, just like you use any number.
     1) **Second Option**: forgo the while loop and just use the `sorted()` function instead. Take a look at how it works [here](https://www.w3schools.com/python/ref_func_sorted.asp)      
4) Finish by printing the final list and printing the discarded list.
   For instance, if you named your final list **final_list** you can do: `print("The final list is:", final_list)`

## How should the script work in practice?

You should start with the following list as initial list:
```python
initial_list = [9, 2, 43, -10, 25, 10, 7, 4, 11]
```

Your output should be:\
`The final list is [25, 3, 2, 1]`.\
`The discarded list is [43, -10, 7, 11]`

Why these numbers? The script should start one number at a time from the initial_list, the first one being **9**:
- The script checks *2 i* but 9 is not negative, so it moves to the next condition, *2 ii*.
- It sees that 9 is indeed odd, so it moves to the first of the sibling conditions, *2 ii a*
- 9 is divisible by 3, so the final list should get the result of 9 divided by 3, which is 3.

The script should now move to another loop, checking for the next item, **2**
- The script checks *2 i* but 2 is not negative, so it skips to the next condition, *2 ii*.
- 2 is not odd, so the script ignores all of *2 ii* subconditions (*2 ii a, 2 ii b, and 2 ii c*) and move straight to *2 iii*
- 2 is even, so the final list should have the result of 2 divided by 2, which is 1.

The script shoul now move to another loop, checking for the next item **43**
- The script checks *2 i* but 43 is not negative, so it moves to the next item, *2 ii*.
- 43 is odd so it will move to the first of the sibling condition, *2 ii a*
- 43 is not divisible by 3, so the script will move to *2 ii b*
- 43 is not divisible by 5, so the script will move to *2 ii c*
- Since neither *2 ii a* nor *2 ii b* were met, the script tells us to add 43 to the discarded list.

The script should now move to another loop, checking for the next item... and so it will go with the rest of the numbers of the initial list. After all the numbers were checked and modified, you'll just need to sort the list, which you know how to do. However, this time they must be in the *descendant* order!

## Important notes and hints

### You should never modify a list while running a **for loop** on it! It breaks!
   - The python way of doing things is you modify the value and send that value to another list.
   - If you have operations that can't be done at the same time (which is the case in this assignment), consider having an intermediate list for that.
   - For example, start with list A, run a **for loop** to do certain operations on it and send results to list B. Once the for loop is over and list B is complete, run a **for loop** on list B to do whatever other changes on it and send it to list C.
     
### How to check if a number is divisible by another number
  - For that, you need to use the **module** operator ( `%` ). It returns the remainder of a division. If you need to fresh up, take a look at ["What Is Dividend Divisor Quotient Remainder Formula?"](https://www.cuemath.com/dividend-divisor-quotient-remainder-formula/)
   - For instance, in 13 divided by 3:
      - 13 is the dividend
      - 3 is the divisor
      - 4 is the quotient
      - 1 is the remainder

In Python, you can get a normal division (with a floating point number as a result with the `/` operator, get only the quotient with the `//` operator and get only the remainder with `%` operator (which is the one that matters for us in this assignment). Therefore:
     
- `13 / 3` returns 4.3333
- `13 // 3` returns 4
- `13 % 3` returns 1

Therefore, to check if a number is divisible by another, what we are really asking is if the **remainder** is equal to zero or not.

- `7 % 2` **is not** equal to zero, so 7 is not divisible by 2.
- `16 % 2` **is** equal to zero, so 16 is divisible by 2.
    
For evens and odds it's the same thing. A number is even if it's divisible by 2, and it is odd if it is not divisible by 2.
    
### How **if**, **elif**, **else** work
To learn how these work, take a look at [this guide](https://www.programiz.com/python-programming/if-elif-else)
Have fun!

