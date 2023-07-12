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
- Expected result: web - sending does not occur, an error appears near the "Invalid format" field;
  DB - information is not updated

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
- Values: 19 characters, including latin beech