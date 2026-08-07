# Sodacards\DefaultApi



All URIs are relative to https://api.sodacards.com, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**deleteWebhook()**](DefaultApi.md#deleteWebhook) | **DELETE** /v1/webhooks/{id} | Delete a webhook endpoint |
| [**getBalance()**](DefaultApi.md#getBalance) | **GET** /v1/balance | Get wallet balance |
| [**getOrder()**](DefaultApi.md#getOrder) | **GET** /v1/orders/{id} | Get an order |
| [**getProduct()**](DefaultApi.md#getProduct) | **GET** /v1/products/{id} | Get a product |
| [**listCatalog()**](DefaultApi.md#listCatalog) | **GET** /v1/catalog | List catalog products |
| [**listOrders()**](DefaultApi.md#listOrders) | **GET** /v1/orders | List orders |
| [**listWebhooks()**](DefaultApi.md#listWebhooks) | **GET** /v1/webhooks | List webhook endpoints |
| [**ping()**](DefaultApi.md#ping) | **GET** /v1/ping | Ping |
| [**placeOrder()**](DefaultApi.md#placeOrder) | **POST** /v1/orders | Place an order |
| [**registerWebhook()**](DefaultApi.md#registerWebhook) | **POST** /v1/webhooks | Register a webhook endpoint |
| [**revealOrderCodes()**](DefaultApi.md#revealOrderCodes) | **GET** /v1/orders/{id}/codes | Reveal order codes |
| [**rotateWebhookSecret()**](DefaultApi.md#rotateWebhookSecret) | **POST** /v1/webhooks/{id}/rotate | Rotate a webhook signing secret |


## `deleteWebhook()`

```php
deleteWebhook($id): object
```

Delete a webhook endpoint

DeleteWebhook removes a webhook endpoint.

### Example

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

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**| id is the webhook endpoint to remove. | |

### Return type

**object**

### Authorization

[ApiKeyAuth](../../README.md#ApiKeyAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`, `application/problem+json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getBalance()`

```php
getBalance(): \Sodacards\Model\SodacardsDevpublicV1GetBalanceResponse
```

Get wallet balance

GetBalance returns the reseller's prepaid wallet balance, the same funds a  live order is settled from. It reads only the caller's own wallet. A test key  reads a fixed sandbox balance, never the real one, so a test integration can  exercise the read without seeing production funds.

### Example

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

try {
    $result = $apiInstance->getBalance();
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling DefaultApi->getBalance: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**\Sodacards\Model\SodacardsDevpublicV1GetBalanceResponse**](../Model/SodacardsDevpublicV1GetBalanceResponse.md)

### Authorization

[ApiKeyAuth](../../README.md#ApiKeyAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`, `application/problem+json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getOrder()`

```php
getOrder($id): \Sodacards\Model\SodacardsDevpublicV1GetOrderResponse
```

Get an order

GetOrder returns one of the reseller's orders by id, with its lines and  current status. A live key reads live orders and a test key reads its own  sandbox orders; an id that is not the caller's is reported as not found.

### Example

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
$id = 'id_example'; // string | id is the order id, from PlaceOrder.

try {
    $result = $apiInstance->getOrder($id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling DefaultApi->getOrder: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**| id is the order id, from PlaceOrder. | |

### Return type

[**\Sodacards\Model\SodacardsDevpublicV1GetOrderResponse**](../Model/SodacardsDevpublicV1GetOrderResponse.md)

### Authorization

[ApiKeyAuth](../../README.md#ApiKeyAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`, `application/problem+json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getProduct()`

```php
getProduct($id): \Sodacards\Model\SodacardsDevpublicV1GetProductResponse
```

Get a product

GetProduct returns a single product by its id, priced for the reseller. The  id is the one carried by a catalog entry. A product the reseller may not see  (unlisted, hidden or inactive) is reported as not found, so an id cannot be  probed to learn what exists outside the reseller's catalog.

### Example

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
$id = 'id_example'; // string | id is the product id, taken from a catalog entry.

try {
    $result = $apiInstance->getProduct($id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling DefaultApi->getProduct: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**| id is the product id, taken from a catalog entry. | |

### Return type

[**\Sodacards\Model\SodacardsDevpublicV1GetProductResponse**](../Model/SodacardsDevpublicV1GetProductResponse.md)

### Authorization

[ApiKeyAuth](../../README.md#ApiKeyAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`, `application/problem+json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `listCatalog()`

```php
listCatalog($limit, $cursor): \Sodacards\Model\SodacardsDevpublicV1ListCatalogResponse
```

List catalog products

ListCatalog returns a page of the products the reseller may sell, each with  the reseller's price. It is cursor-paginated: pass next_cursor from the  previous page to fetch the next. A product's id is the identifier used to  order it.

### Example

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
$limit = 56; // int | limit is the maximum number of products to return (1..100). Zero applies the  default page size.
$cursor = 'cursor_example'; // string | cursor is the next_cursor of the previous page. Empty for the first page.

try {
    $result = $apiInstance->listCatalog($limit, $cursor);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling DefaultApi->listCatalog: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **limit** | **int**| limit is the maximum number of products to return (1..100). Zero applies the  default page size. | [optional] |
| **cursor** | **string**| cursor is the next_cursor of the previous page. Empty for the first page. | [optional] |

### Return type

[**\Sodacards\Model\SodacardsDevpublicV1ListCatalogResponse**](../Model/SodacardsDevpublicV1ListCatalogResponse.md)

### Authorization

[ApiKeyAuth](../../README.md#ApiKeyAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`, `application/problem+json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `listOrders()`

```php
listOrders($limit, $cursor, $reference): \Sodacards\Model\SodacardsDevpublicV1ListOrdersResponse
```

List orders

ListOrders returns a page of the reseller's orders, newest first. It is  cursor-paginated: pass next_cursor from the previous page to fetch the next.  A live key lists live orders and a test key lists its own sandbox orders.

### Example

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
$limit = 56; // int | limit is the maximum number of orders to return (1..100). Zero applies the  default page size.
$cursor = 'cursor_example'; // string | cursor is the next_cursor of the previous page. Empty for the first page.
$reference = 'reference_example'; // string | reference, when set, filters the list to the orders carrying that client  reference. The cursor is ignored when a reference is given.

try {
    $result = $apiInstance->listOrders($limit, $cursor, $reference);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling DefaultApi->listOrders: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **limit** | **int**| limit is the maximum number of orders to return (1..100). Zero applies the  default page size. | [optional] |
| **cursor** | **string**| cursor is the next_cursor of the previous page. Empty for the first page. | [optional] |
| **reference** | **string**| reference, when set, filters the list to the orders carrying that client  reference. The cursor is ignored when a reference is given. | [optional] |

### Return type

[**\Sodacards\Model\SodacardsDevpublicV1ListOrdersResponse**](../Model/SodacardsDevpublicV1ListOrdersResponse.md)

### Authorization

[ApiKeyAuth](../../README.md#ApiKeyAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`, `application/problem+json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `listWebhooks()`

```php
listWebhooks(): \Sodacards\Model\SodacardsDevpublicV1ListWebhooksResponse
```

List webhook endpoints

ListWebhooks returns the reseller's registered webhook endpoints. It never  returns their signing secrets.

### Example

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

try {
    $result = $apiInstance->listWebhooks();
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling DefaultApi->listWebhooks: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**\Sodacards\Model\SodacardsDevpublicV1ListWebhooksResponse**](../Model/SodacardsDevpublicV1ListWebhooksResponse.md)

### Authorization

[ApiKeyAuth](../../README.md#ApiKeyAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`, `application/problem+json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `ping()`

```php
ping(): \Sodacards\Model\SodacardsDevpublicV1PingResponse
```

Ping

Ping confirms a key works and reports which reseller and environment it  authenticated as. It is the health check a developer hits first.

### Example

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

try {
    $result = $apiInstance->ping();
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling DefaultApi->ping: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**\Sodacards\Model\SodacardsDevpublicV1PingResponse**](../Model/SodacardsDevpublicV1PingResponse.md)

### Authorization

[ApiKeyAuth](../../README.md#ApiKeyAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`, `application/problem+json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `placeOrder()`

```php
placeOrder($idempotency_key, $sodacards_devpublic_v1_place_order_request): \Sodacards\Model\SodacardsDevpublicV1PlaceOrderResponse
```

Place an order

PlaceOrder buys one or more products, settled from the reseller's prepaid  wallet. It is asynchronous: the order is accepted and fulfilled in the  background, so the response carries the order id and a status to poll. The  request MUST carry an Idempotency-Key header, so a retried request never  places a second order.

### Example

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
$idempotency_key = 'idempotency_key_example'; // string | A unique key so a retried request never places a second order. Reuse the same key to retry a call safely; reusing it with a different body is a conflict.
$sodacards_devpublic_v1_place_order_request = new \Sodacards\Model\SodacardsDevpublicV1PlaceOrderRequest(); // \Sodacards\Model\SodacardsDevpublicV1PlaceOrderRequest

try {
    $result = $apiInstance->placeOrder($idempotency_key, $sodacards_devpublic_v1_place_order_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling DefaultApi->placeOrder: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **idempotency_key** | **string**| A unique key so a retried request never places a second order. Reuse the same key to retry a call safely; reusing it with a different body is a conflict. | |
| **sodacards_devpublic_v1_place_order_request** | [**\Sodacards\Model\SodacardsDevpublicV1PlaceOrderRequest**](../Model/SodacardsDevpublicV1PlaceOrderRequest.md)|  | |

### Return type

[**\Sodacards\Model\SodacardsDevpublicV1PlaceOrderResponse**](../Model/SodacardsDevpublicV1PlaceOrderResponse.md)

### Authorization

[ApiKeyAuth](../../README.md#ApiKeyAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`, `application/problem+json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `registerWebhook()`

```php
registerWebhook($sodacards_devpublic_v1_register_webhook_request): \Sodacards\Model\SodacardsDevpublicV1RegisterWebhookResponse
```

Register a webhook endpoint

RegisterWebhook registers a URL to receive signed event deliveries. The URL  must be HTTPS and publicly routable. The response carries the signing secret  once; store it, as it is never shown again.

### Example

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
$sodacards_devpublic_v1_register_webhook_request = new \Sodacards\Model\SodacardsDevpublicV1RegisterWebhookRequest(); // \Sodacards\Model\SodacardsDevpublicV1RegisterWebhookRequest

try {
    $result = $apiInstance->registerWebhook($sodacards_devpublic_v1_register_webhook_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling DefaultApi->registerWebhook: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **sodacards_devpublic_v1_register_webhook_request** | [**\Sodacards\Model\SodacardsDevpublicV1RegisterWebhookRequest**](../Model/SodacardsDevpublicV1RegisterWebhookRequest.md)|  | |

### Return type

[**\Sodacards\Model\SodacardsDevpublicV1RegisterWebhookResponse**](../Model/SodacardsDevpublicV1RegisterWebhookResponse.md)

### Authorization

[ApiKeyAuth](../../README.md#ApiKeyAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`, `application/problem+json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `revealOrderCodes()`

```php
revealOrderCodes($id): \Sodacards\Model\SodacardsDevpublicV1RevealOrderCodesResponse
```

Reveal order codes

RevealOrderCodes returns the delivered codes of a completed order. Codes are  available once the order is completed; a still-processing order reports that  it is not ready. Reveals are rate-limited per order.

### Example

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
$id = 'id_example'; // string | id is the order whose codes to reveal.

try {
    $result = $apiInstance->revealOrderCodes($id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling DefaultApi->revealOrderCodes: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**| id is the order whose codes to reveal. | |

### Return type

[**\Sodacards\Model\SodacardsDevpublicV1RevealOrderCodesResponse**](../Model/SodacardsDevpublicV1RevealOrderCodesResponse.md)

### Authorization

[ApiKeyAuth](../../README.md#ApiKeyAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`, `application/problem+json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `rotateWebhookSecret()`

```php
rotateWebhookSecret($id): \Sodacards\Model\SodacardsDevpublicV1RotateWebhookSecretResponse
```

Rotate a webhook signing secret

RotateWebhookSecret issues a new signing secret for an endpoint without  interrupting deliveries: the new secret is returned once, and the previous one  stays valid until prev_secret_expires_at. During that window deliveries are  signed with both, so switch your verification to the new secret before the  deadline. Rotating again replaces the outgoing secret rather than adding a  third, so at most two secrets are ever accepted at once.

### Example

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
$id = 'id_example'; // string | id is the webhook endpoint whose signing secret to rotate.

try {
    $result = $apiInstance->rotateWebhookSecret($id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling DefaultApi->rotateWebhookSecret: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**| id is the webhook endpoint whose signing secret to rotate. | |

### Return type

[**\Sodacards\Model\SodacardsDevpublicV1RotateWebhookSecretResponse**](../Model/SodacardsDevpublicV1RotateWebhookSecretResponse.md)

### Authorization

[ApiKeyAuth](../../README.md#ApiKeyAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`, `application/problem+json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)
