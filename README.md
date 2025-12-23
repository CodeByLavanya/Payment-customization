1. Storefront (Theme Customization)Requirements => Done
* On Product Detail Page (PDP):
* Add a Purchase Type selector:
* One-Time Purchase
* Subscription
* Store selection in cart as:
* Show badge in cart:
* One-Time Purchase
* Subscription
* Retain selection on:
* Page reload
* Variant change
Evaluation Focus
* Liquid + JS integration
* Cart properties usage
* Clean DOM handling
line_item.properties.purchase_type

2. Custom Shopify App (Admin App)Requirements
Create a custom Shopify app (Node.js / Remix) with an Admin UI that allows:
* Enable / Disable Payment Customization Rules
* Configure:
* Hide Cash on Delivery for Subscription items
* Rename payment method for OTP:
* Bogus Gateway → Bogus (OTP Eligible)
Data Storage
* App Metafields OR
* App database (preferred)
Example Settings
{"hide_cod_for_subscription": true,"rename_bogus_for_otp": true } 

3. Shopify Function – Payment Customization Function 
Function Responsibilities

Inspect cart contents and modify payment methods dynamically.
Rules to ImplementRule 1: Subscription in Cart
* If any cart line has:
* Then:
* Hide Cash on Delivery
Rule 2: OTP-Only Cart
* If all items are:
* Then:
* Rename:
* Bogus Gateway → Bogus (OTP Eligible)
Expected Skills
* Shopify Payment Customization API
* Cart line inspection
* Conditional logic
* Clean function structure

4. Checkout UI ExtensionRequirements => Done
Create a Checkout UI Extension that:
* Displays an info banner:
* “Certain payment methods are unavailable for subscription items.”
* If both OTP + Subscription items exist:
* Show warning:
“Cash on Delivery is disabled because your cart contains subscription products.”
* If OTP-only:
* Show success message:
“All payment methods are available for One-Time Purchase items.”
Placement
* Checkout footer OR Order Summary

5. WebhooksRequired Webhooks
* orders/create
* orders/paid
On Trigger, Log:
* Order ID
* Selected payment method
* OTP item count
* Subscription item count
* Payment status
