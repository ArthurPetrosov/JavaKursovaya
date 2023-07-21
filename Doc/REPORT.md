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


<img width="1303" alt="Screenshot 2023-07-20 at 23 34 08" src="https://github.com/ArthurPetrosov/JavaKursovaya/assets/125126241/bbdeffa4-f461-4daf-b7f8-cb564a0f0f03">


## General recommendations

Based on the test results, the following bug reports were filed:

- [Ввод данных для отказной карты в форму "Оплата по карте" или "Кредит по данным карты" появляется уведомление об успешной операции #1](https://github.com/SeniorTe/Diploma/issues/1)
- [После отправки пустой формы "Оплата по карте" или "Кредит по данным карты" отображаются некорректные ошибки #2](https://github.com/ArthurPetrosov/JavaKursovaya/issues/2)
- [После отправки карты не находящейся в списке проверочных карт от разработчиков в форму "Оплата по карте" или "Кредит по данным карты" операция обрабатывается #3](https://github.com/ArthurPetrosov/JavaKursovaya/issues/3)
- [В форме "Оплата по карте" или "Кредит по данным карты" при закрытии поля об ошибке появляется уведомление об успешной операции #4](https://github.com/ArthurPetrosov/JavaKursovaya/issues/4)
- [При вводе невалидных значений в форму "Оплата по карте" или "Кредит по данным карты" в поле "Владелец" символы отображаются и форма отправляет данные в обработку #5](https://github.com/ArthurPetrosov/JavaKursovaya/issues/5)
- [При вводе нулевого значения в поле "Месяц" в форму "Оплата по карте" или "Кредит по данным карты" происходит отправка формы #6](https://github.com/ArthurPetrosov/JavaKursovaya/issues/6)
- [При попытке отправить форму "Оплата по карте" или "Кредит по данным карты"с пустым полем "CVC/CVV" поле "Владелец" показывает неверное сообщение об ошибке #7](https://github.com/ArthurPetrosov/JavaKursovaya/issues/7)
- [При вводе срока действия карты более 5 лет от текущего месяца, форма считывает значение как валидное #8](https://github.com/ArthurPetrosov/JavaKursovaya/issues/8)
  

Blocking bugs weren't found, the main function of the service is to sell tours, a scenario in which the payment would not go through, although it should not be found.
The first and tenth Issues can be fixed immediately by making a hotfix. The first bug carries the risk of selling the tour on an inactive card, and the tour can be bought, for example, with a blocked credit card. The last bug carries reputational risks, people will not want to buy a tour from an operator who does not know how to spell the city correctly.
The remaining bugs can be added to the backlog, prioritized and fixed as the resource becomes available.
