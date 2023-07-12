### Test report

Automation was carried out on the Purchase form
All main scenarios were automated: Happy path and validation of all forms on the page

38 test cases were implemented, 12 of them revealed defects.
Successful scenarios - 68.42%

Adding information to the database occurs as expected
The main errors were found in the work of the web form:
- incorrect display of errors for all forms on the page (affects usability)
- the absence of any restrictions when entering the name of the cardholder (leads to errors in filling out the form)
- entering card data that was not provided for testing does not show errors
- incorrectly calculated card life limit

<img width="661" alt="Screenshot 2023-07-11 at 19 09 31" src="https://github.com/ArthurPetrosov/JavaKursovaya/assets/125126241/3ab46185-500e-4fe5-a8d9-5e878345daa7">
