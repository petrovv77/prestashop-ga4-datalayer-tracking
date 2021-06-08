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
- Event Name: purchase
- Data Layer Variables (Name - Data Layer Variable Name) :
- - Ecommerce Items - ecommerce.items
- - Ecommerce Transaction ID - ecommerce.transaction_id
- - Ecommerce Value - ecommerce.value
- - Ecommerce Tax - ecommerce.tax
- - Ecommerce Shipping - ecommerce.shipping
- - Ecommerce Currency - ecommerce.currency
- Event Parameters (Parameter Name - Value):
- - items - {{Ecommerce Items}}
- - transaction_id - {{Ecommerce Transaction ID}}
- - value - {{Ecommerce Value}}
- - tax - {{Ecommerce Tax}}
- - shipping - {{Ecommerce Shipping}}
- - currency - {{Ecommerce Currency}}
- Trigger: event equals purchase

# Ecommerce (GA4)
help: https://developers.google.com/tag-manager/ecommerce-ga4#measure_purchases
