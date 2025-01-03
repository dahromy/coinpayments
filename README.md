# CoinPayments PHP library
This is basic PHP library for [CoinPayments API](https://goo.gl/mj98qm). It's written without any external dependencies and it allows you to add your own HTTP agents like Guzzle.
[CoinPayments](https://goo.gl/mj98qm) is one of the largest cryptocurrency payment processors. They support over few hundred cryptocurrencies. Amongst those are better known 
Bitcoin, Litecoin, Ethereum, Monero... some lesser known/used coins like Ubiq, Peercoin, GameCredits and they even support shitcoins like Ripple.

## Sample usage


```php
use Sigismund\CoinPayments;

$coinPaymentsAPI = new CoinPayments($merchantID, $publicKey, $privateKey, $ipnSecret);

// Get conversion rates for all supported currencies
$rates = $coinPaymentsAPI->getRates();

// Sample transaction for 16$
$coinPaymentsAPI->createTransaction(16, 'USD', 'BTC', $additional = []);
```

## Getting Started

### Requirements

* PHP >= 7.0

This library does not have any external dependencies. 


### Installation

The recommended way to install this library is through Composer.


```sh
# Install Composer
curl -sS https://getcomposer.org/installer | php
```
Next, run the Composer command to install the latest stable version of CoinPayments PHP library:

```sh
composer require sigismund/coinpayments
```

After installing, you need to require Composer's autoloader:
```php
require 'vendor/autoload.php';
```

You can then later update library using composer:
```sh
composer.phar update
```

## Configuration

To use the CoinPayments library, you need to set up your credentials. The `CoinPayments` class constructor requires four parameters: `merchantID`, `publicKey`, `privateKey`, and `ipnSecret`.

```php
use Sigismund\CoinPayments\CoinPayments;

$merchantID = 'your-merchant-id';
$publicKey = 'your-public-key';
$privateKey = 'your-private-key';
$ipnSecret = 'your-ipn-secret';

$coinPaymentsAPI = new CoinPayments($merchantID, $publicKey, $privateKey, $ipnSecret);
```

## Usage

Once you have configured your credentials, you can use the `CoinPayments` class to interact with the CoinPayments API. Here are some examples:

### Get Conversion Rates

```php
$rates = $coinPaymentsAPI->getRates();
```

### Create a Transaction

```php
$amount = 16.00;
$currencyIn = 'USD';
$currencyOut = 'BTC';
$additional = [];

$transaction = $coinPaymentsAPI->createTransaction($amount, $currencyIn, $currencyOut, $additional);
```

### Get Basic Account Info

```php
$basicInfo = $coinPaymentsAPI->getBasicInfo();
```

## API Commands

The `Commands` class defines the available API commands. Here is a list of the commands:

* `Commands::CREATE_TRANSACTION`
* `Commands::CREATE_TRANSFER`
* `Commands::CREATE_WITHDRAWAL`
* `Commands::GET_TX_INFO`
* `Commands::BALANCES`
* `Commands::RATES`
* `Commands::GET_CALLBACK_ADDRESS`
* `Commands::BASIC_INFO`
* `Commands::GET_DEPOSIT_ADDRESS`
* `Commands::GET_TX_IDS`

## Testing
... all pull requests are welcome ;)

## Contributing

Please read CONTRIBUTING.md for details on our code of conduct, and the process for submitting pull requests to us.

## Versioning

We use [SemVer](http://semver.org/) for versioning. For the versions available, see the [tags on this repository](https://github.com/sigismund/coinpayments/tags). 

## Authors

* **Žiga Drnovšček** - *Initial work* - [Sigismund](https://github.com/sigismund)

See also the list of [contributors](https://github.com/sigismund/coinpayments/contributors) who participated in this project.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details

## Acknowledgments

* Hat tip to anyone who's code was used
* Inspiration
* etc
