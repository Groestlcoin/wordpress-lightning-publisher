# Lightning Publisher for WordPress

Lightning Publisher for WordPress allows you to offer previews of your blog posts and require a Lightning Network payment to release the rest.

Powered by :zap: [Lightning Charge](https://github.com/Groestlcoin/lightning-charge).

## Installation

1. Setup [Lightning Charge](https://github.com/Groestlcoin/lightning-charge).

2. [download wordpress-lightning-publisher.zip](https://github.com/groestlcoin/wordpress-lightning-publisher/releases)
   and install it manually.

3. Under the WordPress administration panel, go to `Settings -> Lightning Publisher` to configure your Lightning Charge server URL and API token.

Note that Lightning Publisher uses Lightning Charge's built-in checkout page (as an iframe),
meaning that the Lightning Charge server has to be publicly accessible to users.
If users need to access it using a different URL than the one used for communicating with the API,
set this under "Public URL" in the settings page.

## Usage

Add `[ifpaid AMOUNT CURRENCY]` in the place that marks the beginning of paid access to the post. All text prior to that point will be available as a preview to everyone, while all text after that point will only be available to patrons.

For example: `[ifpaid 0.0005 USD]` or `[ifpaid 0.00000005 GRS]`. All the currencies on Coingecko are supported. GRS amounts can have up to 11 decimal places (milli-satoshis precision).

You may also specify a custom message and button text, as follows: `[ifpaid 0.005 ILS text="Please pay to continue reading." button="Alright, I'll pay!"]`.

Once the user makes the payment, the page will automatically refresh and the access token will be appended to the URL. The user can bookmark this patron-only URL to return to the content later.
The token does not currently ever expire.

Note that anyone with this URL will be able to access the content. There are currently no restrictions in place to prevent links from being shared.

## License

MIT
