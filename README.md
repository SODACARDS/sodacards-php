# SODACARDS PHP SDK

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](./LICENSE)
[![Docs](https://img.shields.io/badge/docs-developers.sodacards.com-003087.svg)](https://developers.sodacards.com)

The official PHP client for the [SODACARDS Developer API](https://developers.sodacards.com) — sell gift cards and game top-ups from your own systems, across West Africa.

Browse the catalog, place orders, retrieve delivered codes, and subscribe to webhooks.

## Requirements

PHP 8.1 or newer, with the Guzzle HTTP client (installed automatically by Composer).

## Installation

```sh
composer require sodacards/sdk
```

## Authentication

Every request is authenticated with an API key that you generate from the [developer dashboard](https://developers.sodacards.com). Keys are prefixed `sc_live_` (production) or `sc_test_` (sandbox); the sandbox returns fake codes so you can integrate safely.

Load the key from the environment — never hard-code it in source.

```php
$config = Sodacards\Configuration::getDefaultConfiguration()
    ->setApiKey('X-API-Key', getenv('SODACARDS_API_KEY'));
```

## Quickstart

```php
<?php

require_once __DIR__ . '/vendor/autoload.php';

$config = Sodacards\Configuration::getDefaultConfiguration()
    ->setApiKey('X-API-Key', getenv('SODACARDS_API_KEY'));

$api = new Sodacards\Api\DefaultApi(new GuzzleHttp\Client(), $config);

// 1. Discover what you can sell.
$catalog = $api->listCatalog();

// 2. Place an order for one product.
$request = new Sodacards\Model\SodacardsDevpublicV1PlaceOrderRequest([
    'lines' => [
        new Sodacards\Model\SodacardsDevpublicV1OrderLine([
            'product_id' => 'prod_123',
            'quantity'   => 1,
        ]),
    ],
    'reference' => 'my-internal-ref-0001',
]);
$order = $api->placeOrder($request);

// 3. Read back the delivered codes once the order is fulfilled.
$codes = $api->revealOrderCodes($order->getOrder()->getId());
print_r($codes);
```

## Idempotency

`placeOrder` is the only state-changing call. Send an `Idempotency-Key` header so a retried request never creates a duplicate order — the API returns the original order for a repeated key.

## Operations

| Method | Description |
| --- | --- |
| `listCatalog` | List sellable products (cursor-paginated). |
| `getProduct` | Fetch a single product by id. |
| `placeOrder` | Buy one or more products. |
| `getOrder` | Retrieve an order by id. |
| `listOrders` | List your orders (cursor-paginated). |
| `revealOrderCodes` | Reveal the delivered codes for a fulfilled order. |
| `registerWebhook` | Subscribe an endpoint to events. |
| `listWebhooks` | List your webhook endpoints. |
| `deleteWebhook` | Remove a webhook endpoint. |
| `ping` | Health check for your credentials. |

## Pagination

List endpoints use cursor (keyset) pagination. Pass the `nextCursor` returned by a response as the `cursor` of the next call until it is empty.

## Errors

Failed requests throw `Sodacards\ApiException`, which carries the HTTP status and the API error body.

## Documentation and support

- API reference and guides: <https://developers.sodacards.com>
- Support: <mailto:support@sodacards.com>

## License

Released under the [MIT License](./LICENSE).

---

This SDK is generated from the SODACARDS OpenAPI specification and is regenerated automatically whenever the API changes. Open issues on the [documentation portal](https://developers.sodacards.com) rather than editing generated files directly.
