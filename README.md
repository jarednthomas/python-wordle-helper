# Python Wordle Helper

A python program that allows you to quickly apply simple regex to a dictionary of five-letter words.

---

The minimum amount of information required for the program to run is a line of a wordle formatted as a string in quotes. 

Do not include correct letters in the wrong place; only put green letters that are correct **and** in the correct place, as this first argument is what creates the regular expression.

---

### Example Usage:

```
python wordle.py '#####'
```

Above, the hashtags (or pound symbols) denote unknown letters, and are the only non-alphabet character allowed in the five letter string; This example would return all 5757 words in the word list. 

### Another Example. 
Say you know after a first guess the middle letter is `z`:

```
python wordle.py '##Z##'
```

Down to just 27 words, now you know after a second guess the word includes `a`, but doesn't inlcude (excludes) `e`. You can pass these in as additional arguments:

```
python wordle.py '##Z##' -i a -e e
```

Just 7 left. You went out on a limb and threw in a `w` on the last guess and it's in the wrong spot. Included and Excluded letters should be passed in the same string:

```
python wordle.py '##Z##' -i aw -e e
```

With the above example, the program would exit, printing out the only word that matches the regex and filters: wazoo. 

Without a single solution, the program will return a list of possible words that match the expression and filters. Double check your arguments if you get no results!