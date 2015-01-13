PHP Round #1
==========

This document contains description and requirements for Round #1 of interview for PHP developer position.

## Goal

1. Verify applicant's ability to work with 3rd party libraries. Verify that applicant is able to write clean and testable code.
2. Check how clean code the applicant is able to create.

## Requirements

1) Create a payment gateway library, that could handle payments with:

* [Paypal REST API](https://developer.paypal.com/docs/api/)
* [Braintree payments](https://www.braintreepayments.com/docs/php/guide/overview)

Library should be designed to easily add another additional payment gateways.

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

## Bonus question

* How would you handle security for saving credit cards?

## Specification

* Create your own sandbox accounts for Paypal and Braintree
* To make it easier, implement only **single payment** with credit card. No need to implement saving credit card and authorization of payments (unless you really want to try it out).
* After submitting the form, use a different gateway based on these rules:
  * if credit card type is AMEX, then use Paypal.
  * if currency is USD, EUR, or AUD, then use Paypal. Otherwise use Braintree.
  * if currency is **not** USD and credit card **is** AMEX, return error message, that AMEX is possible to use only for USD
* Use any PHP framework you want or no framework at all, it's up to you.
* Don't bother with any graphics, just simple HTML, simple form, no CSS needed. Or just use [Twitter Bootstrap](http://getbootstrap.com).
* Use only Paypal, Braintree PHP libraries. You can use jQuery for form validations. Do not use any other 3rd party libraries.
* Cover code with unit tests.
* The code needs to work after we clone it and try it (no bugs) and should process the payments.

## Quality requirements

Similarly as during any other code review in our team, we'll be checking the following:

* code quality
* usage of the configuration files
* usage of the unit tests
* naming convention

