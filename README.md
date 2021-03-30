# Files And Exceptions 
**Chapter 10** shows you how to work with files and handle errors so your programs won’t crash unexpectedly. You’ll store data before your program closes, and read the data back in when the program runs again. You’ll learn about Python’s exceptions, which allow you to anticipate errors, and make your programs handle those errors gracefully.

Updates ---

Some of the text files from [Project Gutenberg](https://www.gutenberg.org/) are now encoded as utf-8. This can result in a `UnicodeDecodeError` when trying to open the file. This can be addressed by adding an argument when we call `open()`, which explicitly tells Python which encoding to use when opening the file.  For example, in the program [*alice.py*](alice.py) on pages 203-204, the first lines of the program should look like this:

```python     filename = 'alice_new.txt'

    try:
        with open(filename, encoding='utf-8') as f_obj:
            contents = f_obj.read()
```

The `encoding` argument should be added to the `open()` calls in [*word_count.py*](word_count.py) as well on pages 205-206.

<span id="page_197"></span>

<span id="page_197"></span>

TRY IT YOURSELF \#1
-------------------

<span id="ch10exe1"></span>**10-1. Learning Python:** Open a blank file in your text editor and write a few lines summarizing what you’ve learned about Python so far. Start each line with the phrase *In Python you can...*. Save the file as *learning_python.txt* in the same directory as your exercises from this chapter. Write a program that reads the file and prints what you wrote three times. Print the contents once by reading in the entire file, once by looping over the file object, and once by storing the lines in a list and then working with them outside the `with` block.

<span id="ch10exe2"></span>**10-2. Learning C:** You can use the `replace()` method to replace any word in a string with a different word. Here’s a quick example showing how to replace `'dog'` with `'cat'`
in a sentence:

``` python >>> message = "I really like dogs."
>>> message.replace('dog', 'cat')
'I really like cats.'
```

Read in each line from the file you just created, *learning_python.txt*,
and replace the word *Python* with the name of another language, such as *C*. Print each modified line to the screen.

TRY IT YOURSELF \#2
-------------------

<span id="ch10exe3"></span>**10-3. Guest:** Write a program that prompts the user for their name. When they respond, write their name to a file called *guest.txt*.

<span id="ch10exe4"></span>**10-4. Guest Book:** Write a `while` loop that prompts users for their name. When they enter their name, print a greeting to the screen and add a line recording their visit in a file called *guest_book.txt*. Make sure each entry appears on a new line in the file.

<span id="ch10exe5"></span>**10-5. Programming Poll:** Write a `while`
loop that asks people why they like programming. Each time someone enters a reason, add their reason to a file that stores all the responses.

TRY IT YOURSELF \#3
-------------------

<span id="ch10exe6"></span>**10-6. Addition:** One common problem when prompting for numerical input occurs when people provide text instead of numbers. When you try to convert the input to an `int`, you’ll get a `TypeError`. Write a program that prompts for two numbers. Add them together and print the result. Catch the `TypeError` if either input value is not a number, and print a friendly error message. Test your program by entering two numbers and then by entering some text instead of a number.

<span id="page_208"></span><span id="ch10exe7"></span>**10-7. Addition Calculator:** Wrap your code from [Exercise 10-6](#ch10exe6) in a `while` loop so the user can continue entering numbers even if they make a mistake and enter text instead of a number.

<span id="ch10exe8"></span>**10-8. Cats and Dogs:** Make two files,
*cats.txt* and *dogs.txt*. Store at least three names of cats in the first file and three names of dogs in the second file. Write a program that tries to read these files and print the contents of the file to the screen. Wrap your code in a `try-except` block to catch the `FileNotFound` error, and print a friendly message if a file is missing.
Move one of the files to a different location on your system, and make sure the code in the `except` block executes properly.

<span id="ch10exe9"></span>**10-9. Silent Cats and Dogs:** Modify your `except` block in [Exercise 10-8](#ch10exe8) to fail silently if either file is missing.

<span id="ch10exe10"></span>**10-10. Common Words:** Visit Project Gutenberg (*<http://gutenberg.org/>*) and find a few texts you’d like to analyze. Download the text files for these works, or copy the raw text from your browser into a text file on your computer.

You can use the `count()` method to find out how many times a word or phrase appears in a string. For example, the following code counts the number of times `'row'` appears in a string:

``` python >>> line = "Row, row, row your boat"
>>> line.count('row')
2
>>> line.lower().count('row')
3
```

Notice that converting the string to lowercase using `lower()` catches all appearances of the word you’re looking for, regardless of how it’s formatted.

Write a program that reads the files you found at Project Gutenberg and determines how many times the word `'the'` appears in each text.

TRY IT YOURSELF \#4
-------------------

<span id="ch10exe11"></span>**10-11. Favorite Number:** Write a program that prompts for the user’s favorite number. Use `json.dump()` to store this number in a file. Write a separate program that reads in this value and prints the message, “I know your favorite number! It’s \_\_\_\_\_.”

<span id="ch10exe12"></span>**10-12. Favorite Number Remembered:**
Combine the two programs from [Exercise 10-11](#ch10exe11) into one script. If the specified number is already stored, report the favorite number to the user. If not, prompt for the user’s favorite number and store it by appending to the JSON file. Run the program twice to see that it works.

<span id="ch10exe13"></span>**10-13. Verify User:** The final listing for [*remember_me.py*](remember_me.py) assumes either that the user has already entered their username or that the program is running for the first time. We should modify it in case the current user is not the person who last used the program.

Before printing a welcome back message in `greet_user()`, ask the user if this is the correct username. If it’s not, call `get_new_username()`
to get the correct username.


&nbsp; | &nbsp; | &nbsp; | &nbsp;
----|----|----|----
[&#10094; Prev](../../../pcc-chapter-09)| &nbsp; | &nbsp; | &nbsp;[Next &#10095;](../../../pcc-chapter-11)
