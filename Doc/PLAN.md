# **List of automated scripts:**

**1. Payment by card: valid data - happy path**
- Valid data: card - 1111 2222 3333 4444; month - 11; year - 27; owner - Anastasiia; cvc/cvv - 123
- Expected result: web - the appearance of information about the successful completion of the operation; DB - operation status "APPROVED"

**2. Payment by card: refused card - happy path**
- Valid data: card - 5555 6666 7777 8888; month - 11; year - 25; owner - Anastasiia; cvc/cvv - 123
- Expected result: web - the appearance of information about the unsuccessful operation; DB - operation status "DECLINED"

**3. Card payment: attempt to submit an empty form**
- Values: all fields remain blank
- Expected result: web - sending does not occur, an error appears for each field "Required field";
  DB - information is not updated

**4. Payment by card: checking the validation of the "Card number" field (enter valid values in the remaining fields)**
4.1 Empty field
- Values: leave the field empty
- Expected result: web - sending does not occur, an error appears near the field "Required field";
  DB - information is not updated

  4.2 Card number not from the list of developers
- Values: 16 digits that are not APPROVED/DECLINED card numbers
- Expected result: the system is refused after submitting the form and verifying the data in the emulator of banking services

4.3 Limit value
- Values: 15 first digits of the APPROVED card
- Expected result: web - sending does not occur, an error appears near the "Invalid format" field;
  DB - information is not updated

4.4 Limit value
- Values: Attempt to enter 17 characters in a field
- Expected result: web - 17th character is not displayed

4.5 Invalid characters
- Values: attempt to enter a Latin/Cyrillic letter, special character
- Expected result: web - the symbol is not displayed

**5. Payment by card: checking the validation of the "Month" field (in other fields enter valid values, the card is APPROVED)**
5.1 Empty field
- Values: leave the field empty
- Expected result: web - sending does not occur, an error appears near the field "Required field";
  DB - information is not updated

5.2 Limit value
- Values: 1 digit
- Expected result: web - sending does not occur, an error appears near the "Invalid format" field;
  DB - information is not updated

5.3 Limit value
- Values: number 13
- Expected result: web - an error appears near the field "Invalid card expiration date"

5.4 Limit value
- Values: 00
- Expected result: web - an error appears near the field "Invalid card expiration date"

  5.5 Limit value
  - Values: Attempt to enter the 3rd character
  - Expected result: web - 3rd character is not displayed

  5.6 Invalid characters
- Values: attempt to enter a Latin/Cyrillic letter, special character
- Expected result: web - the symbol is not displayed

  5.7 Limit value
  - Values: number 12
  - Expected result: web - the appearance of information about the successful completion of the operation; DB - operation status "APPROVED"

5.8 Limit value
- Values: 01
- Expected result: web - the appearance of information about the successful completion of the operation; DB - operation status "APPROVED"

**6. Payment by card: checking the validation of the "Year" field (in other fields enter valid values, the card is APPROVED)**
6.1 Empty field
- Values: leave the field empty
- Expected result: web - sending does not occur, an error appears near the field "Required field";
  DB - information is not updated

6.2 Limit value
- Values: 1 digit
- Expected result: web - sending does not occur, an error appears near the "Invalid format" field;
  DB - information is not updated

6.3 Limit value
- Values: current month + 4 years 11 months (59 months)
- Expected result: web - an error appears near the field "Incorrect expiration date of the card"

6.4 Limit value
- Values: current month + 5 years 1 month (61 months)
- Expected result: web - an error appears near the "Card expired" field

6.5 Limit value
- Values: Attempt to enter the 3rd character
- Expected result: web - 3rd character is not displayed

6.6 Invalid characters
- Values: attempt to enter a Latin/Cyrillic letter, special character
- Expected result: web - the symbol is not displayed

6.7 Limit value
- Values: number 26
- Expected result: web - the appearance of information about the successful completion of the operation; DB - operation status "APPROVED"

**7. Payment by card: checking the validation of the "Owner" field (in other fields enter valid values, the card is APPROVED)**
7.1 Empty field
- Values: leave the field empty
- Expected result: web - sending does not occur, an error appears at the field "Required field";
  DB - information is not updated

7.2 Invalid characters
- Values: attempt to enter a Cyrillic letter, special character except "." and "-", a number
- Expected result: web - the symbol is not displayed

7.3 Limit value
- Values: 19 characters, including latin letters, symbols "." And "-"
- Expected result: web - the appearance of information about the successful completion of the operation; DB - operation status "APPROVED"

7.4 Limit value
- Values: attempt to enter 21 valid characters
- Expected result: symbol is not displayed

**8. Payment by card: checking the validation of the field "CVC / CVV" (in other fields enter valid values, the card is APPROVED)**
8.1 Empty field
- Values: leave the field empty
- Expected result: web - sending does not occur, an error appears at the field "Required field";
   DB - information is not updated

8.2 Limit value
- Values: 2 digits
- Expected result: web - sending does not occur, an error occurs near the field "Invalid format"

8.3 Limit value
- Values: attempt to enter the 4th digit
- Expected result: symbol is not displayed

8.4 Invalid characters
- Values: attempt to enter a Latin/Cyrillic letter, special character
- Expected result: web - the symbol is not displayed

**9. Credit payment: valid data - happy path**
- Valid data: card - 1111 2222 3333 4444; month - 11; year - 27; owner - Anastasiia; cvc/cvv - 123
- Expected result: web - the appearance of information about the successful completion of the operation; DB - operation status "APPROVED"

**10. Payment on credit: refusal card - happy path**
- Valid data: card - 5555 6666 7777 8888; month - 11; year - 25; owner - Anastasiia; cvc/cvv - 123
- Expected result: web - the appearance of information about the unsuccessful operation; DB - operation status "DECLINED"

**eleven. Credit payment: attempt to submit an empty form**
- Values: all fields remain blank
- Expected result: web - sending does not occur, an error appears for each field "Required field";
   DB - information is not updated

**12. Payment on credit: checking the validation of the "Card number" field (enter valid values in the remaining fields)**
12.1 Empty field
- Values: leave the field empty
- Expected result: web - sending does not occur, an error appears at the field "Required field";
   DB - information is not updated

     12.2 Card number not from the list of developers
- Values: 16 digits that are not APPROVED/DECLINED card numbers
- Expected result: web - sending does not occur, an error appears near the "Invalid format" field;
   DB - information is not updated

12.3 Limit value
- Values: 15 first digits of the APPROVED card
- Expected result: web - sending does not occur, an error appears near the "Invalid format" field;
DB - information is not updated

12.4 Limit value
- Values: Attempt to enter 17 characters in a field
- Expected result: web - 17th character is not displayed

12.5 Invalid characters
- Values: attempt to enter a Latin/Cyrillic letter, special character
- Expected result: web - the symbol is not displayed

**13. Payment by card: checking the validation of the "Month" field (in other fields enter valid values, the card is APPROVED)**
13.1 Empty field
- Values: leave the field empty
- Expected result: web - sending does not occur, an error appears at the field "Required field";
DB - information is not updated

13.2 Limit value
- Values: 1 digit
- Expected result: web - sending does not occur, an error appears near the "Invalid format" field;
DB - information is not updated

13.3 Limit value
- Values: Attempt to enter the 3rd character
- Expected result: web - 3rd character is not displayed
-
13.4 Limit value
- Values: number 12
- Expected result: web - the appearance of information about the successful completion of the operation; DB - operation status "APPROVED"

13.5 Limit value
- Values: number 13
- Expected result: web - an error appears near the field "Incorrect expiration date of the card"

13.6 Limit value
- Values: 00
- Expected result: web - an error appears near the field "Incorrect expiration date of the card"

13.7 Limit value
- Values: 01
- Expected result: web - the appearance of information about the successful completion of the operation; DB - operation status "APPROVED"

   13.8 Invalid characters
     - Values: attempt to enter a Latin/Cyrillic letter, special character
     - Expected result: web - the symbol is not displayed

**14. Payment by card: checking the validation of the "Year" field (in other fields enter valid values, the card is APPROVED)**
14.1 Empty field
- Values: leave the field empty
- Expected result: web - sending does not occur, an error appears at the field "Required field";
   DB - information is not updated

14.2 Limit value
- Values: 1 digit
- Expected result: web - sending does not occur, an error appears near the "Invalid format" field;
   DB - information is not updated

14.3 Limit value
- Values: Attempt to enter the 3rd character
- Expected result: web - 3rd character is not displayed

14.4 Limit value
- Values: number 26
- Expected result: web - the appearance of information about the successful completion of the operation; DB - operation status "APPROVED"

14.5 Limit value
- Values: number 28
- Expected result: web - an error appears near the field "Incorrect expiration date of the card"

14.6 Limit value
- Values: number 21
- Expected result: web - an error appears near the "Card expired" field

14.7 Invalid characters
- Values: attempt to enter a Latin/Cyrillic letter, special character
- Expected result: web - the symbol is not displayed

**15. Payment by card: checking the validation of the "Owner" field (in other fields enter valid values, the card is APPROVED)**
15.1 Empty field
- Values: leave the field empty
- Expected result: web - sending does not occur, an error appears at the field "Required field";
   DB - information is not updated

15.2 Limit value
- Values: 19 characters, including latin letters, symbols "." And "-"
- Expected result: web - the appearance of information about the successful completion of the operation; DB - operation status "APPROVED"

15.3 Limit value
- Values: 20 characters including latin letters, symbols "." And "-"
- Expected result: web - the appearance of information about the successful completion of the operation; DB - operation status "APPROVED"

15.4 Limit value
- Values: attempt to enter 21 valid characters
- Expected result: symbol is not displayed

15.5 Invalid characters
- Values: attempt to enter a Cyrillic letter, special character except "." and "-", a number
- Expected result: web - the symbol is not displayed

**16. Payment by card: checking the validation of the field "CVC / CVV" (in other fields enter valid values, the card is APPROVED)**
16.1 Empty field
- Values: leave the field empty
- Expected result: web - sending does not occur, an error appears at the field "Required field";
   DB - information is not updated

16.2 Limit value
- Values: 2 digits
- Expected result: web - sending does not occur, an error occurs near the field "Invalid format"

16.3 Limit value
- Values: attempt to enter the 4th digit
- Expected result: symbol is not displayed

16.4 Invalid characters
- Values: attempt to enter a Latin/Cyrillic letter, special character
- Expected result: web - the symbol is not displayed




# List of tools used with justification for the choice:
- IDEA as a development environment, which I used throughout the course
- Docker for connecting containers in which programs to work with the database will be launched
(checking what data is entered into the database after the payment / purchase on credit)
- MySQL to work in the database (launch via Docker), as I have already used it before
- I will build the project on Gradle, I will connect several libraries to it
   - Selenide for working with web forms
   - Faker to generate random names and numbers to fill out the form
   - Commons-dbutils and mysql for connecting to the database in tests
- Basic Gradle reporting to generate information about tests

# List and description of possible risks in automation:

Lack of knowledge about how the database works - difficulty with analyzing data from the database using automation

# Interval assessment taking into account risks (in hours):
- 1 hour project setup (done)
- 3 hours manual testing + filling out reports on the results of defects
- 5 hours preparation for testing
- 4 hours writing attests
- 2 hours reporting on the results of testing
- 2 hours reporting on project results
