# Sentence Analysis Algorithm

## Overview
This algorithm reads a sentence character by character until it reaches the terminating period (`.`). It calculates three values:  

1. The **length** of the sentence (number of characters before the period).  
2. The **number of words** in the sentence (assuming each word is separated by a single space).  
3. The **number of vowels** (A, E, I, O, U in both uppercase and lowercase).  

The algorithm processes each character individually and updates counters as needed.

---

## Pseudocode

ALGORITHM sentence_analysis
VAR
ch : CHARACTER; // variable to store each character
length, words, vowels : INTEGER; // counters for length, words, vowels
BEGIN
length <- 0 // initialize length counter
words <- 1 // assume the first word starts immediately
vowels <- 0 // initialize vowel counter
REPEAT
    Read(ch)                  // read one character

    IF ch <> '.' THEN         // stop counting at the period
        length <- length + 1  // increase length

        // check if character is a space
        IF ch = ' ' THEN
            words <- words + 1
        END_IF

        // check if character is a vowel (uppercase or lowercase)
        IF (ch = 'A') OR (ch = 'E') OR (ch = 'I') OR (ch = 'O') OR (ch = 'U') OR
           (ch = 'a') OR (ch = 'e') OR (ch = 'i') OR (ch = 'o') OR (ch = 'u') THEN
            vowels <- vowels + 1
        END_IF
    END_IF
UNTIL (ch = '.')              // loop ends at the period

// display results
Write("Length = ", length)
Write("Words = ", words)
Write("Vowels = ", vowels)
END

---

## Example Run

### Input
I am fine.

### Trace
- Length = 9  
- Words = 3  
- Vowels = 4  

### Output
Length = 9
Words = 3
Vowels = 4

---

## Key Notes
- Words are assumed to be separated by exactly one space.  
- The period (`.`) is not counted in the sentence length.  
- Both uppercase and lowercase vowels are recognized.  

---

## Pascal Implementation

Below is a working Pascal version of the pseudocode:

```pascal
program SentenceAnalysis;

var
    ch: char;
    length, words, vowels: integer;

begin
    length := 0;
    words := 1;      { assume at least one word }
    vowels := 0;

    repeat
        read(ch);

        if ch <> '.' then
        begin
            length := length + 1;

            if ch = ' ' then
                words := words + 1;

            if (ch in ['A','E','I','O','U','a','e','i','o','u']) then
                vowels := vowels + 1;
        end;
    until ch = '.';

    writeln('Length = ', length);
    writeln('Words = ', words);
    writeln('Vowels = ', vowels);
end.
________________________________________
Example Run in Pascal
Input
Hello World.
Output
Length = 11
Words = 2
Vowels = 3
________________________________________

