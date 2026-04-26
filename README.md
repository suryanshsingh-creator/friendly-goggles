# friendly-goggles
Trying make a full working website to check whether a credit card is real or not by testing the credit card number using luhn algorithm. 
*The work on the website has not yet started.*

Credit Card Validator (Luhn Algorithm)
A lightweight C++ console application that validates credit card numbers using the Luhn Algorithm. This program ensures that a card number is syntactically valid before any actual transaction processing would occur.

🧠How the Algorithm Works
The Luhn algorithm validates a number by checking its internal checksum:

From right to left, every second digit is doubled (starting from the second-to-last digit).

If doubling a digit results in a number greater than 9, the digits of the result are added together (or simply subtract 9).

All digits (the modified even-position digits and the original odd-position digits) are summed.

If the total sum modulo 10 equals 0, the number is valid.

🚀 Features
Reverse Traversal: Correctly processes digits from right to left, as required by the algorithm.

Robust Input Handling: Uses std::string to prevent integer overflow for long card numbers.

Input Sanitization: Includes a check to ensure the input contains only numeric digits and provides detailed error messages for non-digit characters.

Debug Logs: (Currently commented out in code) allows for easy tracking of how each digit is processed.

🛠️ Code Structure
Functions
sumOddDigit: Processes the 1st, 3rd, 5th, etc., digits from the right. It converts the character to an integer and adds it to the total.

sumEvenDigit: Processes the 2nd, 4th, 6th, etc., digits from the right. It doubles the digit and applies the "minus 9" rule if the result exceeds 9.

main: Handles user input, calls the validation logic, and prints the final result.

Key Logic Snippet
C++
// Logic for doubling even-position digits
long digit = (card_number[i] - '0') * 2;
even_sum += (digit > 9) ? (digit - 9) : digit;

💻 How to Run
Compile:

Bash
g++ card_validator.cpp -o validator
Run:

Bash
./validator

Test:
Enter a card number (e.g., a 16-digit Visa or MasterCard number) without spaces or dashes.

⚠️ Requirements
A C++ compiler (supporting C++11 or higher).

Input should be digits only (no spaces, hyphens, or letters).
