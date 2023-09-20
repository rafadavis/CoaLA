# Extra Assignment

To practice your new skills in Python loops and conditionals, try this harder assignment

1- Write a script from scratch.

You can, of course, take a look at your other script for hints on how to do things. I encourage you *not* to copy it, because it can make it more confusing for yourself. Not everything that is there will be useful here, and some things will even make the new script not work properly.
Think about what you want to do, and check what parts of the old script will be repeated in the new script, what parts will not, and what else will still need to be done.

2- Your new script should check a list of numbers and will print a final list with modifications to these numbers. These are the modifications:

   a) If the number is zero or negative, the final list should not show it at all.
   b) If the number is odd:
      b.1) If the number is divisible by 3, the final list should have the result of the number divided by 3
      b.2) If the number is divisible by 5, the final list should have the number unmodified.
      b.3) If the number is odd, is not divisible by 3, and is not divisible by 5, don't send it to the final list, but send a message telling that the number does not feet any of the criteria
   c) If the number is even, the final list should have the result of that number divided by 2
   d) All discarded numbers should go to a `discarded_list`.

3- The final list, should have numbers in descending order.
   You can do that in two ways:
      1- By modifying the while loop of your previous script
        In this route, you will need these two lines:
	`import math` (just like I did in the previous script)
	`negative_infinity = -math.inf` (notice that in your previous script you used "regular" (positive) infinity, but this time you'll need negative infinity. Why? Think about the operations you want do to sort in the descending order.
      2- By forgoing the while loop completely and using the `sorted()` function. Take a look at how it works [here](https://www.w3schools.com/python/ref_func_sorted.asp)
      
4- Finish by printing the final list and printing the discarded list.
   For instance, if you named your final list **final_list** you can do: `print("The final list is:", final_list)`

## How does the script look like in practice?

You should start with the following list as initial list:
    `initial_list = [9, 2, 43, -10, 25, 10, 7, 4, 11]`

Your final list should be `[25, 3, 2, 1]` and your discarded list should be `[43, -10, 7, 11]`

Why? Let's check the first item:
- 9 is not negative, so the script ignores *a*
- 9 is odd, so the script will check the next condition, *b1*
- 9 is divisible by 3, so the final list should get the result of 9 divided by 3, which is 3.

Let's check another one:
- 2 is not negative, so the script ignores *a*
- 2 is not odd, so the script ignores *b* and all of *b* subconditions (*b1*, *b2*, *b3*)
- 2 is even, so the final list should have the result of 2 divided by 2, which is 1.

One more:
- 43 is not negative, so the script ignores *a*
- 43 is odd so the script will check the next condition, *b1*
- 43 is not divisible by 3, so the script will check the next condition, *b2*
- Since 43 is odd, not divisible by 3, and not divisible by 5, the script tells us to discard it.

And so it goes with the rest of numbers.

## Important notes and hints

1. You should never modify a list while running a **for loop** on it! It breaks! The python way of doing things is you modify the value and send that value to another list.
   If you have operations that can't be done at the same time, consider having an intermediate list for that. For example, start with list A, run a **for loop** to do certain operations on it and send results to list B. Once the for loop is over and list B is complete, run a **for loop** on list B to do whatever other changes on it and send it to list C.

2. How to check if a number is divisible by another number

For that, you need to use the **module** operator ( `%` ). It returns the remainder of a division. If you need to fresh up, take a look at ["What Is Dividend Divisor Quotient Remainder Formula?"](https://www.cuemath.com/dividend-divisor-quotient-remainder-formula/)

For instance, in 13 divided by 3:
      - 13 is the dividend
      - 3 is the divisor
      - 4 is the quotient
      - 1 is the remainder

   In Python, you can get a normal division (with a floating point number as a result with the `/` operator, get only the quotient with the `//` operator and get only the remainder with `%` operator (which is the one that matters for us in this assignment).

So:
   `13 / 3` returns 4.3333
   `13 // 3` returns 4
   `13 % 3` returns 1
   
Therefore, to check if a number is divisible by another, what we are really asking is if the **remainder** is equal to zero or not.

`7 % 2` **is not** equal to zero, so 7 is not divisible by 2.
`16 % 2` **is** equal to zero, so 16 is divisible by 2.

For evens and odds it's the same thing. A number is even if it's divisible by 2, and it is odd if it is not divisible by 2.

3. How **if**, **elif**, **else** work
   You can read more [here](https://www.programiz.com/python-programming/if-elif-else)

