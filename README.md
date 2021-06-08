This repository is a needed part for getting the Google Tag Manager tracking conversions correctly in 
PrestaShop. 

## add page view transaction tracking to your shop
Adding page view tracking is super simple. Adding conversion tracking requires a data layer, which I added with this module.

IMPORTANT: For this code to fire, your payment method modules need to be calling PrestaShop after payment. E.g. here are the changes I needed to make to get this to happen with PayPal. As far as I can tell, this "problem" exists for both my module, and for the PrestaShop Google Analytics module.

Install the PrestaShop module "Data Layer Module" (instructions for installing a PrestaShop module can be found in the PrestaShop Documentation). 
It's a VERY basic module that any PHP coder can understand and expand on.

## Inside GTM 

Tag configuration for this example:
- Tag type: GA4 Event
- Event Name: begin_checkout
- Event Parameter (name - value): 'items' - {{Ecommerce Items}}
- Variable Type: data layer Variable - 'ecommerce.items'
- Trigger: event equals begin_checkout

# Ecommerce (GA4)
help: https://developers.google.com/tag-manager/ecommerce-ga4#measure_purchases
