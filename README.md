PHP Round #1
==========

This document contains description and requirements for Round #1 of interview for PHP developer position.

## Goal
Verify applicant's ability to work with 3rd party libraries. Verify that applicant is able to write clean and testable code.

## Requirements
1) Create Payment gateway library, that could handle payments with:

* [Paypal REST API](https://developer.paypal.com/docs/api/)
* [Braintree payments](https://www.braintreepayments.com/docs/php/guide/overview)

Library should be designed for adding another payment gateways.

2) Create a simple form for making payment. Form should have this fields:

* Credit card holder name
* Currency (USD, EUR, THB, HKD, SGD, AUD)
* Full name
* Credit card number
* Credit card expiration
* Credit card ccv

Show success or error message after payment.
Use appropriate form validations.

3) Save order data + response from payment gateway to database table.

4) Fork this library on github, push your solution and request pull request. 

## Specification
* Create your own sandbox accounts for Paypal and Braintree
* Implement only single payment with credit card. No need to implement saving credit card and authorization of payments.
* Use different gateway based on this rules:
  * if credit card type is AMEX, use Paypal
  * if currency is USD, EUR, or AUD, use Paypal. Use Braintree for others
  * if currency is **not** USD and credit card is AMEX, return error message, that AMEX is possible to use only for USD
* Use any PHP framework you want or no framework at all, it's up to you.
* Don't bother with any graphics, just simple HTML.
* Use only Paypal and Braintree PHP libraries, no other 3rd party library.
* Cover code with Unit tests

## Bonus question
* How would you handle security for saving credit cards?
