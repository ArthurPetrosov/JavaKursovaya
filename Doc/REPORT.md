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

![Screenshot 2023-07-11 at 18.29.16.png](..%2F..%2F..%2F..%2F..%2Fvar%2Ffolders%2F9k%2Fbw8j7swx7fd4hf61zfr_jj9m0000gn%2FT%2FTemporaryItems%2FNSIRD_screencaptureui_FOcHMs%2FScreenshot%202023-07-11%20at%2018.29.16.png)