# sodacards

Sell gift cards and game top-ups from your own systems.


## Installation & Usage

### Requirements

PHP 8.1 and later.

### Composer

To install the bindings via [Composer](https://getcomposer.org/), add the following to `composer.json`:

```json
{
  "repositories": [
    {
      "type": "vcs",
      "url": "https://github.com/GIT_USER_ID/GIT_REPO_ID.git"
    }
  ],
  "require": {
    "GIT_USER_ID/GIT_REPO_ID": "*@dev"
  }
}
```

Then run `composer install`

### Manual Installation

Download the files and include `autoload.php`:

```php
<?php
require_once('/path/to/sodacards/vendor/autoload.php');
```

## Getting Started

Please follow the [installation procedure](#installation--usage) and then run the following:

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



// Configure API key authorization: ApiKeyAuth
$config = Sodacards\Configuration::getDefaultConfiguration()->setApiKey('X-API-Key', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// $config = Sodacards\Configuration::getDefaultConfiguration()->setApiKeyPrefix('X-API-Key', 'Bearer');


$apiInstance = new Sodacards\Api\DefaultApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 'id_example'; // string | id is the webhook endpoint to remove.

try {
    $result = $apiInstance->deleteWebhook($id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling DefaultApi->deleteWebhook: ', $e->getMessage(), PHP_EOL;
}

```

## API Endpoints

All URIs are relative to *https://api.sodacards.com*

Class | Method | HTTP request | Description
------------ | ------------- | ------------- | -------------
*DefaultApi* | [**deleteWebhook**](docs/Api/DefaultApi.md#deletewebhook) | **DELETE** /v1/webhooks/{id} | DeleteWebhook
*DefaultApi* | [**getOrder**](docs/Api/DefaultApi.md#getorder) | **GET** /v1/orders/{id} | GetOrder
*DefaultApi* | [**getProduct**](docs/Api/DefaultApi.md#getproduct) | **GET** /v1/products/{id} | GetProduct
*DefaultApi* | [**listCatalog**](docs/Api/DefaultApi.md#listcatalog) | **GET** /v1/catalog | ListCatalog
*DefaultApi* | [**listOrders**](docs/Api/DefaultApi.md#listorders) | **GET** /v1/orders | ListOrders
*DefaultApi* | [**listWebhooks**](docs/Api/DefaultApi.md#listwebhooks) | **GET** /v1/webhooks | ListWebhooks
*DefaultApi* | [**ping**](docs/Api/DefaultApi.md#ping) | **GET** /v1/ping | Ping
*DefaultApi* | [**placeOrder**](docs/Api/DefaultApi.md#placeorder) | **POST** /v1/orders | PlaceOrder
*DefaultApi* | [**registerWebhook**](docs/Api/DefaultApi.md#registerwebhook) | **POST** /v1/webhooks | RegisterWebhook
*DefaultApi* | [**revealOrderCodes**](docs/Api/DefaultApi.md#revealordercodes) | **GET** /v1/orders/{order_id}/codes | RevealOrderCodes

## Models

- [Amount](docs/Model/Amount.md)
- [SodacardsDevpublicV1DeleteWebhookRequest](docs/Model/SodacardsDevpublicV1DeleteWebhookRequest.md)
- [SodacardsDevpublicV1GetOrderRequest](docs/Model/SodacardsDevpublicV1GetOrderRequest.md)
- [SodacardsDevpublicV1GetOrderResponse](docs/Model/SodacardsDevpublicV1GetOrderResponse.md)
- [SodacardsDevpublicV1GetProductRequest](docs/Model/SodacardsDevpublicV1GetProductRequest.md)
- [SodacardsDevpublicV1GetProductResponse](docs/Model/SodacardsDevpublicV1GetProductResponse.md)
- [SodacardsDevpublicV1ListCatalogRequest](docs/Model/SodacardsDevpublicV1ListCatalogRequest.md)
- [SodacardsDevpublicV1ListCatalogResponse](docs/Model/SodacardsDevpublicV1ListCatalogResponse.md)
- [SodacardsDevpublicV1ListOrdersRequest](docs/Model/SodacardsDevpublicV1ListOrdersRequest.md)
- [SodacardsDevpublicV1ListOrdersResponse](docs/Model/SodacardsDevpublicV1ListOrdersResponse.md)
- [SodacardsDevpublicV1ListWebhooksResponse](docs/Model/SodacardsDevpublicV1ListWebhooksResponse.md)
- [SodacardsDevpublicV1Money](docs/Model/SodacardsDevpublicV1Money.md)
- [SodacardsDevpublicV1Order](docs/Model/SodacardsDevpublicV1Order.md)
- [SodacardsDevpublicV1OrderItem](docs/Model/SodacardsDevpublicV1OrderItem.md)
- [SodacardsDevpublicV1OrderItemInputFieldsEntry](docs/Model/SodacardsDevpublicV1OrderItemInputFieldsEntry.md)
- [SodacardsDevpublicV1OrderLine](docs/Model/SodacardsDevpublicV1OrderLine.md)
- [SodacardsDevpublicV1OrderLineInputFieldsEntry](docs/Model/SodacardsDevpublicV1OrderLineInputFieldsEntry.md)
- [SodacardsDevpublicV1PingResponse](docs/Model/SodacardsDevpublicV1PingResponse.md)
- [SodacardsDevpublicV1PlaceOrderRequest](docs/Model/SodacardsDevpublicV1PlaceOrderRequest.md)
- [SodacardsDevpublicV1PlaceOrderResponse](docs/Model/SodacardsDevpublicV1PlaceOrderResponse.md)
- [SodacardsDevpublicV1PlacedOrder](docs/Model/SodacardsDevpublicV1PlacedOrder.md)
- [SodacardsDevpublicV1Product](docs/Model/SodacardsDevpublicV1Product.md)
- [SodacardsDevpublicV1ProductFaceValue](docs/Model/SodacardsDevpublicV1ProductFaceValue.md)
- [SodacardsDevpublicV1RegisterWebhookRequest](docs/Model/SodacardsDevpublicV1RegisterWebhookRequest.md)
- [SodacardsDevpublicV1RegisterWebhookResponse](docs/Model/SodacardsDevpublicV1RegisterWebhookResponse.md)
- [SodacardsDevpublicV1RevealOrderCodesRequest](docs/Model/SodacardsDevpublicV1RevealOrderCodesRequest.md)
- [SodacardsDevpublicV1RevealOrderCodesResponse](docs/Model/SodacardsDevpublicV1RevealOrderCodesResponse.md)
- [SodacardsDevpublicV1RevealedCode](docs/Model/SodacardsDevpublicV1RevealedCode.md)
- [SodacardsDevpublicV1Webhook](docs/Model/SodacardsDevpublicV1Webhook.md)

## Authorization

Authentication schemes defined for the API:
### ApiKeyAuth

- **Type**: API key
- **API key parameter name**: X-API-Key
- **Location**: HTTP header


## Tests

To run the tests, use:

```bash
composer install
vendor/bin/phpunit
```

## Author



## About this package

This PHP package is automatically generated by the [OpenAPI Generator](https://openapi-generator.tech) project:

- API version: `1.0.0`
    - Generator version: `7.24.0`
- Build package: `org.openapitools.codegen.languages.PhpClientCodegen`
