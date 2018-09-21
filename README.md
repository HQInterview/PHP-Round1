PHP Round #1
==========

This document contains description and requirements for Round #1 of interview for PHP developer position.

## Goal

1. Verify applicant's ability to work with 3rd party libraries. Verify that applicant is able to write clean and testable code.
2. Check how clean code the applicant is able to create.

## Requirements

1) Create a payment gateway library, that could handle payments with these 2 gateways:
* [Adyen](https://www.adyen.com/)
* [Braintree](https://www.braintreepayments.com/)

Payment gateway library should be designed to easily add another additional payment gateways.

2) Create a simple form for making payment. Form should have this fields:

* In order section:
  * Price (amount)
  * Currency (USD, EUR, THB, HKD, SGD, AUD)
  * Customer Full name
* In payment section:
  * Credit card holder name
  * Credit card number
  * Credit card expiration
  * Credit card CCV
* Submit button

Show success or error message after payment. 

Use appropriate form validations.

3) Save order data + response from payment gateway to database table.

4) Create a public repository on Github and push the solution there. Send us the link to the repository.

## Specification

* Create your own sandbox accounts for Adyen and Braintree
* To make it easier, implement only single direct credit card payment, below are their documentations:
    * [Braintree: Sale request](https://developers.braintreepayments.com/reference/request/transaction/sale/php)
    * [Adyen: Payment request](https://docs.adyen.com/developers/api-reference/payments-api/paymentrequest)
* After submitting the form, use a different gateway based on these rules:
  * if credit card type is AMEX, then use Adyen.
  * if currency is USD, EUR, or AUD, then use Adyen. Otherwise use Braintree.
  * if currency is **not** USD and credit card **is** AMEX, return error message, that AMEX is possible to use only for USD
* Use any PHP framework you want or no framework at all, it's up to you.
* Don't bother with any graphics, just simple HTML, simple form, no CSS needed. Or just use [Twitter Bootstrap](http://getbootstrap.com).
* Use only Adyen, Braintree PHP libraries. You can use jQuery for form validations. Do not use any other 3rd party libraries.
* Cover code with unit tests.
* The code needs to work after we clone it and try it (no bugs) and should process the payments.
* Tips: the specifications mentions above are important to our decision, please follow :)

## Quality requirements

Similarly as during any other code review in our team, we'll be checking the following:

* code quality
* usage of the configuration files
* usage of the unit tests
* naming convention
