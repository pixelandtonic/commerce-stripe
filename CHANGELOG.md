# Release Notes for Stripe for Craft Commerce

## 5.0.2 - 2024-08-07

- Fixed a bug where SCA payment sources prevented subscriptions from starting. ([#304](https://github.com/craftcms/commerce-stripe/pull/304))
- Fixed a bug where the `hiddenClass` payment form parameter was not being applied correctly. ([#288](https://github.com/craftcms/commerce-stripe/pull/288))
- Fixed a SQL performance issue that occurred when upgrading. ([#190](https://github.com/craftcms/commerce-stripe/issues/190))
- Fixed a bug the billing issues payment form did not display correctly for subscriptions.
- Fixed a bug where the first payment source created was not set as the default.

## 5.0.1 - 2024-04-09

- Fixed a bug where floating point rounding precision could cause payments/refunds to fail. ([#296](https://github.com/craftcms/commerce-stripe/pull/296))
- Fixed a PHP error that could occur when handling a webhook request. ([#294](https://github.com/craftcms/commerce-stripe/issues/294))

## 5.0.0 - 2024-03-25

- Stripe now requires Craft Commerce 5.0.0-beta.1 or later.