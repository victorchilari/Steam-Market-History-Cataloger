# Steam Market History Cataloger

Steam Market History Cataloger is a Chrome extension used for loading and storing your listings from the [Steam Community Market](https://steamcommunity.com/market). Steam does not offer this data in a format that is easily consumible for those that need extensive information of their transactions. This tool aims to fulfill that role in a user-friendly way.

## Installation

To use this extension, please install it from the [Chrome Web Store](https://chrome.google.com/webstore/detail/dhpcikljplaooekklhbjohojbjbinega).

## Features

-   Loads transactions from the [Steam Community Market](https://steamcommunity.com/market) in any language or currency. Listings are stored to a local database in your browser for use at any time.
-   Allows viewing and filtering of all data loaded in a neat and responsive format within the extension.
-   Transaction data can be exported to JSON and CSV. Data models for JSON can be found [below](#models).
-   Loads purchase history from your [Steam account history](https://store.steampowered.com/account/history). However, this data is not persisted to the extension.
-   Allows background loading. Not enabled by default. Enable this option from the preferences page. Loads are polled at an interval of 1 hour.
-   History pages at <https://steamcommunity.com/market> are displayed 100 results per page. More options are provided which allow you to move around your history easier.

## Models

<!-- Generated by documentation.js. Update this documentation by updating the source code. -->

#### Table of Contents

-   [ListingsJSON](#listingsjson)
    -   [Properties](#properties)
-   [Currency](#currency)
    -   [Properties](#properties-1)
-   [Listing](#listing)
    -   [Properties](#properties-2)
-   [AccountTransaction](#accounttransaction)
    -   [Properties](#properties-3)
-   [GameItem](#gameitem)
    -   [Properties](#properties-4)

### ListingsJSON

The output data when exporting listings to JSON.

Type: [Object](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Object)

#### Properties

-   `currency` **[Currency](#currency)** The currency of for your Steam wallet.
-   `listings` **[Array](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Array)&lt;[Listing](#listing)>** An array of listings.

### Currency

A currency used for prices.

Type: [Object](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Object)

#### Properties

-   `wallet_code` **[number](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Number)** The ID of the currency from Steam.
-   `code` **[string](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/String)** ISO 4217 currency code e.g. "USD".
-   `symbol` **[string](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/String)** Currency symbol e.g. "$".
-   `precision` **[number](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Number)** Decimal place precision e.g. 2 decimal places for USD.
-   `thousand` **[string](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/String)** Thousand place character.
-   `decimal` **[string](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/String)** Decimal place character.
-   `spacer` **[boolean](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Boolean)?** Whether the amount should be displayed with a space between the number and symbol.
-   `after` **[boolean](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Boolean)?** Whether the symbol should be displayed after the number.
-   `trim_trailing` **[boolean](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Boolean)?** Whether trailing zeroes should be trimmed on whole values.
-   `format_precision` **[number](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Number)?** Decimal place precision used in formatting.

### Listing

A listing from your Steam market history at <https://steamcommunity.com/market/>.

Type: [Object](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Object)

#### Properties

-   `transaction_id` **[string](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/String)** Transaction ID.
-   `appid` **[string](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/String)** App ID.
-   `contextid` **[string](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/String)** Context ID.
-   `classid` **[string](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/String)** Class ID.
-   `instanceid` **[string](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/String)** Instance ID.
-   `index` **[number](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Number)** Index of listing in history.
-   `price` **[number](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Number)** Integer value of price formatted to the precision defined by its currency e,g. 100 for $1.00.
-   `is_credit` **[boolean](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Boolean)** Whether the transaction resulted in credit or not.
-   `name` **[string](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/String)** Name.
-   `market_name` **[string](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/String)** Market name.
-   `market_hash_name` **[string](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/String)** Market hash name.
-   `icon` **[string](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/String)** Icon path on Steam's CDN.
-   `name_color` **[string](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/String)?** 6-digit hexademical color for name.
-   `background_color` **[string](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/String)?** 6-digit hexademical color for background.
-   `date_acted` **[Date](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Date)** Date acted.
-   `date_listed` **[Date](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Date)** Date listed.

### AccountTransaction

A row from your Steam account purchase history at <https://store.steampowered.com/account/history/>.

Type: [Object](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Object)

#### Properties

-   `transaction_type` **[number](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Number)** A value fom ETransactionType.
-   `date` **[Date](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Date)** Date of transaction.
-   `count` **[number](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Number)** Number of this type of transaction.
-   `price` **[number](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Number)** Integer value of price formatted to the precision defined by its currency e,g. 100 for $1.00.
-   `is_credit` **[boolean](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Boolean)** Whether the transaction resulted in credit or not.

### GameItem

An item from an in-game purchase belonging to an account transaction (currently unused).

Type: [Object](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Object)

#### Properties

-   `app` **[string](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/String)** App name.
-   `count` **[number](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Number)** Number of this particular item.
-   `name` **[string](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/String)** Name.
-   `price` **[number](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Number)** Price of item(s).

## Known Issues

-   Since history results do not usually include the year of the date, the extension must make a best guess for the year. If you have gaps larger than a year in your history results you may experience issues. This issue may or may not be resolved in the future.
-   Any refunded transactions will persist if they were not refunded at the time of loading. There is no way to remove them from your results at this point unless you clear your entire listing data.

## Contributing

You may contribute to this project by opening an [issue](issues) to file a bug report or feature request. If you would like to contribute code, please open an issue explaining what you're changing and submit a pull request.

## Legal

Offered under the [GNU General Public License v2.0](LICENSE). It is offered as-is and without liability or warranty. You are free to modify and redistribute this extension as long as the source is disclosed and it is published under the same license.

Steam Market History Cataloger is not affiliated with Steam or Valve.

## Privacy Policy

This extension requires permissions to <https://steamcommunity.com> and <https://steampowered.com> to load data about your Steam account, as well as data storage to your disk. Stored data is entirely local and not shared anywhere outside of the extension.

## Donations

This project is offered for free. If you've found this project useful you can show your support by donating Steam items or Ethereum.

**Donate Steam items:**  
<https://steamcommunity.com/tradeoffer/new/?partner=119913840&token=ybdKNJEA>

**Donate Ethereum:**  
0xaC13438bD74b266e7da51805dfD650cB37c1709A
