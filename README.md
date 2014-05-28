PHP Round #1
==========

This document contains description and requirements for Round #1 of interview for PHP developer position.

## Goal
Verify applicant's ability to work with 3rd party libraries, with API's. Write clean and maintainable code.

## Requirements
1) Create Payment gateway library, that could handle payments with:

* [Paypal REST API](https://developer.paypal.com/docs/api/)
* [Braintree payments](https://www.braintreepayments.com/docs/php/guide/overview)

Library should be design in a way, that adding another payment gateway can be done without editing common code.

Implement only single payment with credit card.

2) Create a simple form for adding credit card and making payment. Form should have this fields:

* Amount
* Currency (USD, EUR, THB, HKD, SGD, AUD)
* Full name
* Credit card number
* Credit card expiration
* Credit card ccv

Show success or error message after payment.
Use appropriate form validations.

3) Order data + response from payment gateway to database table.

## Specification
* Use different gateway based on this rules:
  * if credit card type is AMEX, use Paypal
  * if currency is USD, EUR, or AUD, use Paypal. Use Braintree for others
  * if currency is **not** USD and credit card is AMEX, return error message, that AMEX is possible to use only for USD
* Use any PHP framework you want or no framework at all, it's up to you.
* Don't bother with any graphics, just simple HTML.
* Use only Paypal and Braintree PHP libraries, no other 3rd party library.
* Cover code with Unit tests

