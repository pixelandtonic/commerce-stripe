# Release Notes for Stripe for Craft Commerce

## Unreleased

- Fixed a bug where subscriptions that had billing issues did not show a payment form correctly.

## 4.1.4 - 2024-07-18

- Stripe for Craft Commerce now requires Craft Commerce 4.6.5 or later.

## 4.1.3 - 2024-07-17

- Stripe for Craft Commerce now requires Craft Commerce 4.6.5 or later.
- Fixed a bug where SCA payment sources prevented subscriptions from starting. ([#304](https://github.com/craftcms/commerce-stripe/pull/304))
- Fixed a bug where the `hiddenClass` payment form parameter was not being applied correctly. ([#288](https://github.com/craftcms/commerce-stripe/pull/288))

## 4.1.2.3 - 2024-06-18

- Fixed a SQL performance issue when upgrading. ([#190](https://github.com/craftcms/commerce-stripe/issues/190))

## 4.1.2.2 - 2024-04-09

- Fixed a PHP error that could occur when handling a webhook request. ([#294](https://github.com/craftcms/commerce-stripe/issues/294))

## 4.1.2.1 - 2024-03-28

- Fixed a bug where floating point rounding precision could cause payments/refunds to fail. ([#296](https://github.com/craftcms/commerce-stripe/pull/296))

## 4.1.2 - 2024-03-25

- Fixed a bug where redirects could break when adding a new payment source. ([#259](https://github.com/craftcms/commerce-stripe/issues/259), [#289](https://github.com/craftcms/commerce-stripe/issues/289))
- Fixed a bug where payment history was not being updated when a payment was made on a subscription. ([#144](https://github.com/craftcms/commerce-stripe/issues/144))
- Subscription plans queries now return more than 100 plans. ([#104](https://github.com/craftcms/commerce-stripe/issues/104))

## 4.1.1 - 2024-01-12

- Fixed a bug where legacy default payment methods were not being set as default. ([#280](https://github.com/craftcms/commerce-stripe/pull/280))
- Fixed a bug that could cause duplicate payment sources to be created. ([#281](https://github.com/craftcms/commerce-stripe/pull/281))
- Fixed a bug where it wasn’t possible to access the Stripe instance from JavaScript. ([#275](https://github.com/craftcms/commerce-stripe/issues/275))
- Fixed a bug where not all enabled payment methods types were being shown when creating a payment source. ([#251](https://github.com/craftcms/commerce-stripe/issues/251), [#160](https://github.com/craftcms/commerce-stripe/pull/160))
- Fixed a bug where changing a partial payment amount wouldn’t update the payment intent. ([#279](https://github.com/craftcms/commerce-stripe/issues/279))

## 4.1.0 - 2023-12-19

- Stripe for Craft Commerce now requires Commerce 4.3.3 or later.
- It is now possible to create SEPA and Bacs Direct Debit payment sources.
- Payment method data is now stored in expanded form within transaction response data. ([#276](https://github.com/craftcms/commerce-stripe/pull/276))
- Billing address information is now passed to the payment intent. ([#257](https://github.com/craftcms/commerce-stripe/issues/257), [#258](https://github.com/craftcms/commerce-stripe/issues/263))
- Fixed a bug where it wasn’t possible to pay using the SEPA Direct Debit payment method. ([#265](https://github.com/craftcms/commerce-stripe/issues/265))
- Fixed a bug where failed PayPal payments would cause infinite redirects. ([#266](https://github.com/craftcms/commerce-stripe/issues/266))
- Fixed a bug where JavaScript files were being served incorrectly. ([#270](https://github.com/craftcms/commerce-stripe/issues/270))
- Added `craft\commerce\stripe\SubscriptionGateway::handlePaymentIntentSucceeded()`.

## 4.0.1.1 - 2023-10-25

- Restored support for backend payments using the old payment form.
- Fixed missing icon.

## 4.0.1 - 2023-09-28

- Fixed a PHP error that occurred when switching a subscription’s plan.

## 4.0.0 - 2023-09-13

- Added support for all of Stripe’s payment methods, including Apple Pay and Google Wallet. ([#223](https://github.com/craftcms/commerce-stripe/issues/223), [#222](https://github.com/craftcms/commerce-stripe/issues/222),[#212](https://github.com/craftcms/commerce-stripe/issues/212))
- Added support for [Stripe Billing](https://stripe.com/billing).
- Added support for [Stripe Checkout](https://stripe.com/payments/checkout).
- Added support for syncing customer payment methods.
- Plans are now kept in sync with Stripe plans. ([#240](https://github.com/craftcms/commerce-stripe/issues/240))
- Customer information is now kept in sync with Stripe customers.
- Improved logging.
- Stripe now uses the `2022-11-15` version of the Stripe API.
- Added the `commerce-stripe/customers/billing-portal-redirect` action.
- Added the `commerce-stripe/customers/create-setup-intent` action.
- Added the `commerce-stripe/sync/payment-methods` command.
- Added `craft\commerce\stripe\events\BuildSetupIntentRequestEvent`.
- Added `craft\commerce\stripe\gateways\PaymentIntents::getBillingPortalUrl()`.
- Removed `craft\commerce\stripe\base\Gateway::normalizePaymentToken()`.
- Removed `craft\commerce\stripe\events\BuildGatewayRequestEvent::$metadata`. `BuildGatewayRequestEvent::$request` should be used instead.
- Deprecated the `commerce-stripe/default/fetch-plans` action.
- Deprecated creating new payment sources via the `commerce/subscriptions/subscribe` action.
- Fixed a bug where `craft\commerce\stripe\base\SubscriptionGateway::getSubscriptionPlans()` was returning incorrectly-formatted data.
