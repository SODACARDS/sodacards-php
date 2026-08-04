# Sodacards\PublicAPIServiceApi

PublicAPIService is the public developer API a reseller calls with an API key.  It is served as REST (via HTTP transcoding) so developers use GET /v1/... and  curl, and its OpenAPI 3.1 spec is generated from this one file. Every method is  authenticated by the API-key gateway that fronts it.

All URIs are relative to https://api.sodacards.com, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**publicAPIServiceGetBalance()**](PublicAPIServiceApi.md#publicAPIServiceGetBalance) | **GET** /v1/balance | GetBalance |
| [**publicAPIServiceRotateWebhookSecret()**](PublicAPIServiceApi.md#publicAPIServiceRotateWebhookSecret) | **POST** /v1/webhooks/{id}/rotate | RotateWebhookSecret |


## `publicAPIServiceGetBalance()`

```php
publicAPIServiceGetBalance(): \Sodacards\Model\SodacardsDevpublicV1GetBalanceResponse
```

GetBalance

GetBalance returns the reseller's prepaid wallet balance, the same funds a  live order is settled from. It reads only the caller's own wallet. A test key  reads a fixed sandbox balance, never the real one, so a test integration can  exercise the read without seeing production funds.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure API key authorization: ApiKeyAuth
$config = Sodacards\Configuration::getDefaultConfiguration()->setApiKey('X-API-Key', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// $config = Sodacards\Configuration::getDefaultConfiguration()->setApiKeyPrefix('X-API-Key', 'Bearer');


$apiInstance = new Sodacards\Api\PublicAPIServiceApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);

try {
    $result = $apiInstance->publicAPIServiceGetBalance();
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling PublicAPIServiceApi->publicAPIServiceGetBalance: ', $e->getMessage(), PHP_EOL;
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
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `publicAPIServiceRotateWebhookSecret()`

```php
publicAPIServiceRotateWebhookSecret($id): \Sodacards\Model\SodacardsDevpublicV1RotateWebhookSecretResponse
```

RotateWebhookSecret

RotateWebhookSecret issues a new signing secret for an endpoint without  interrupting deliveries: the new secret is returned once, and the previous one  stays valid until prev_secret_expires_at. During that window deliveries are  signed with both, so switch your verification to the new secret before the  deadline. Rotating again replaces the outgoing secret rather than adding a  third, so at most two secrets are ever accepted at once.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure API key authorization: ApiKeyAuth
$config = Sodacards\Configuration::getDefaultConfiguration()->setApiKey('X-API-Key', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// $config = Sodacards\Configuration::getDefaultConfiguration()->setApiKeyPrefix('X-API-Key', 'Bearer');


$apiInstance = new Sodacards\Api\PublicAPIServiceApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 'id_example'; // string | id is the webhook endpoint whose signing secret to rotate.

try {
    $result = $apiInstance->publicAPIServiceRotateWebhookSecret($id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling PublicAPIServiceApi->publicAPIServiceRotateWebhookSecret: ', $e->getMessage(), PHP_EOL;
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
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)
