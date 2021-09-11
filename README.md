# Files And Exceptions

Now that you’ve mastered the basic skills you need to write organized
programs that are easy to use, it’s time to think about making your
programs even more relevant and usable. In this chapter you’ll learn to
work with files so your programs can quickly analyze lots of data.
You’ll learn to handle errors so your programs don’t crash when they
encounter unexpected situations. You’ll learn about *exceptions*, which
are special objects Python creates to manage errors that arise while a
program is running. You’ll also learn about the `json` module, which allows you to save user data
so it isn’t lost when your program stops running.




<span id="page_197"></span>
## TRY IT YOURSELF Ⓐ

<span id="ch10exe1"></span>**10-1. Learning Python:** Open a blank file
in your text editor and write a few lines summarizing what you&rsquo;ve
learned about Python so far. Start each line with the phrase *In Python
you can...*. Save the file as *learning_python.txt* in the same
directory as your exercises from this chapter. Write a program that
reads the file and prints what you wrote three times. Print the contents
once by reading in the entire file, once by looping over the file
object, and once by storing the lines in a list and then working with
them outside the `with` block.

<span id="ch10exe2"></span>**10-2. Learning C:** You can use the
`replace()` method to replace any word in a string with a different
word. Here&rsquo;s a quick example showing how to replace `'dog'` with `'cat'`
in a sentence:

``` python
>>> message = "I really like dogs."
>>> message.replace('dog', 'cat')
'I really like cats.'
```

Read in each line from the file you just created, *learning_python.txt*,
and replace the word *Python* with the name of another language, such as
*C*. Print each modified line to the screen.

## TRY IT YOURSELF Ⓑ

<span id="ch10exe3"></span>**10-3. Guest:** Write a program that prompts
the user for their name. When they respond, write their name to a file
called *guest.txt*.

<span id="ch10exe4"></span>**10-4. Guest Book:** Write a `while` loop
that prompts users for their name. When they enter their name, print a
greeting to the screen and add a line recording their visit in a file
called *guest_book.txt*. Make sure each entry appears on a new line in
the file.

<span id="ch10exe5"></span>**10-5. Programming Poll:** Write a `while`
loop that asks people why they like programming. Each time someone
enters a reason, add their reason to a file that stores all the
responses.

## TRY IT YOURSELF Ⓒ

<span id="ch10exe6"></span>**10-6. Addition:** One common problem when
prompting for numerical input occurs when people provide text instead of
numbers. When you try to convert the input to an `int`, you&rsquo;ll get a
`ValueError`. Write a program that prompts for two numbers. Add them
together and print the result. Catch the `ValueError` if either input
value is not a number, and print a friendly error message. Test your
program by entering two numbers and then by entering some text instead
of a number.

<span id="page_208"></span><span id="ch10exe7"></span>**10-7. Addition
Calculator:** Wrap your code from [Exercise 10-6](#ch10exe6) in
a `while` loop so the user can continue entering numbers even if they
make a mistake and enter text instead of a number.

<span id="ch10exe8"></span>**10-8. Cats and Dogs:** Make two files,
*cats.txt* and *dogs.txt*. Store at least three names of cats in the
first file and three names of dogs in the second file. Write a program
that tries to read these files and print the contents of the file to the
screen. Wrap your code in a `try-except` block to catch the
`FileNotFound` error, and print a friendly message if a file is missing.
Move one of the files to a different location on your system, and make
sure the code in the `except` block executes properly.

<span id="ch10exe9"></span>**10-9. Silent Cats and Dogs:** Modify your
`except` block in [Exercise 10-8](#ch10exe8) to fail silently
if either file is missing.

<span id="ch10exe10"></span>**10-10. Common Words:** Visit Project
Gutenberg (*<http://gutenberg.org/>*) and find a few texts you&rsquo;d like to
analyze. Download the text files for these works, or copy the raw text
from your browser into a text file on your computer.

You can use the `count()` method to find out how many times a word or
phrase appears in a string. For example, the following code counts the
number of times `'row'` appears in a string:

``` python
>>> line = "Row, row, row your boat"
>>> line.count('row')
2
>>> line.lower().count('row')
3
```

Notice that converting the string to lowercase using `lower()` catches
all appearances of the word you&rsquo;re looking for, regardless of how it&rsquo;s
formatted.

Write a program that reads the files you found at Project Gutenberg and
determines how many times the word `'the'` appears in each text.

## TRY IT YOURSELF Ⓓ

<span id="ch10exe11"></span>**10-11. Favorite Number:** Write a program
that prompts for the user&rsquo;s favorite number. Use `json.dump()` to store
this number in a file. Write a separate program that reads in this value
and prints the message, &ldquo;I know your favorite number! It&rsquo;s \_\_\_\_\_.&rdquo;

<span id="ch10exe12"></span>**10-12. Favorite Number Remembered:**
Combine the two programs from [Exercise 10-11](#ch10exe11) into
one file. If the number is already stored, report the favorite number to
the user. If not, prompt for the user&rsquo;s favorite number and store it in
a file. Run the program twice to see that it works.

<span id="ch10exe13"></span>**10-13. Verify User:** The final listing
for *remember_me.py* assumes either that the user has already entered
their username or that the program is running for the first time. We
should modify it in case the current user is not the person who last
used the program.

Before printing a welcome back message in `greet_user()`, ask the user
if this is the correct username. If it&rsquo;s not, call `get_new_username()`
to get the correct username.

