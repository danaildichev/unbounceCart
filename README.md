# unbounceCart

![Static Badge](https://img.shields.io/badge/version-1-blue)

Shopping Cart UI for sending customers from an (landing) page to a checkout URL.

-   Handles one or more products and product variations
-   Cart UI is unobtrusive and easily accessible
-   Pleasantly animated additions and product removals
-   Supports coupon codes
-   Supports URL parameter retention
-   Handles currency formatting in USD by default
-   Has a built-in debug mode

I built this shopping cart when I was working for a publishing company. It needed to run on landing pages built with Unbounce's WYSIWYG so we could integrate them into a checkout flow using Checkout Champ as the payment processor. Unbounce and Checkout Champ are popular service providers in the marketing world. If that's you then there's a good chance this shopping cart should work for you with very little configuration. You'll need to replace the example content with your own product names, descriptions, and prices. The cart can be very easily adapted to work for a different payment processor.

Made with jQuery, Bootstrap, and Font Awesome.

## Table of Contents

- [Live Demo](#live-demo)
- [Install](#install)
- [Usage](#usage)
- [API](#api)
- [Issues](#issues)
- [Contributing](#contributing)
- [License](#license)

## Live Demo
[http://danaildichev.net/portfolio/tools-apps/unbounce-cart](http://danaildichev.net/portfolio/tools-apps/unbounce-cart)

## Install

Clone the `index.html` file

## Usage

Update the Cart's initialization JSON to your liking:

<details>

<summary>Show JSON</summary>

```javascript
<script>

// shopping cart config on page load
/*
* ----------
* Initialize
*
* debug affects the checkout function. Set to true for on-page testing. Set to false to make the checkout button
* redirect the user to the checkout target URL
*
* checkout target url should be the base URL of where the browser will be forwarded (no params)
*
* funnelID come from CheckoutChamp CRM
*
* retainUrlParams passes incoming URL parameters to the checkout page
*
* suggested default cart status message is "You have 0 items in your cart"
*
* subtotal should be initialized to 0. i.e. user starts with no cost in cart
*
* coupon code and message are optional. If used both values must be text.
*
* totalQtyInCart is used to store/display the sum of all quantities of items in the cart
*
* ----------
* Cart Items
*
* keys must be unique. e.g. "Product1_PB" vs "Product1_HC". These labels are used in HTML attributes
*
* ids must be unique. e.g. the product ID in the CheckoutChamp CRM. These values are used in HTML attributes
*
* item name value should be unique
*
* item qty should be initialized to 0. i.e. user starts with no items in cart
*
* item's price value must be integer or decimal. Script handles formatting to display prices as USD in the Cart.
* HTML must be manually set up to match these values and formatting.
*
* imgSrc is the path to where the product image is hosted
*
* imgAlt is the alt text of that product's corresponding img element in the cart
*
* */
let Cart =
{
	"debug": true,
	// "debug": false,
	"checkOutTarget": "https://secure-checkout.your-domain.com/",
	"funnelID": "funnel-id", // e.g. "fid3-checkout"
	"retainUrlParams": true,
	"status": "You have 0 items in your cart",
	"subtotal": 0,
	"coupon": "TEST",
	"couponMessage": "This is a test coupon",
	"totalQtyInCart": 0,
	"items":
	{
		"Product1_PB":
		{
			"id": 999,
			"name": "Product 1 Paperback",
			"qty": 0,
			"price": 85,
			"imgSrc": "images/imgPH1.png",
			"imgAlt": "product 1 paperback"
		},
		"Product1_HC":
		{
			"id": 998,
			"name": "Product 1 Hardcover",
			"qty": 0,
			"price": 100,
			"imgSrc": "images/imgPH1.png",
			"imgAlt": "product 1 hardcover"
		},
		"Product2":
		{
			"id": 876,
			"name": "Product 2",
			"qty": 0,
			"price": 200,
			"imgSrc": "images/imgPH2.png",
			"imgAlt": "product 2"
		},
		"Product3":
		{
			"id": 765,
			"name": "Product 3",
			"qty": 0,
			"price": 300,
			"imgSrc": "images/imgPH3.png",
			"imgAlt": "product 3"
		},
	}
};
// end shopping cart config on page load

</script>
```

</details>

## API

The shopping cart is not intended to expose any functions or data.

## Issues

Open an issue or hit me up.

## Contributing

PRs accepted.

## License

GPL-3.0
