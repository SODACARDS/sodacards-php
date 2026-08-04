# Sodacards\PublicAPIServiceApi

PublicAPIService is the public developer API a reseller calls with an API key.  It is served as REST (via HTTP transcoding) so developers use GET /v1/... and  curl, and its OpenAPI 3.1 spec is generated from this one file. Every method is  authenticated by the API-key gateway that fronts it.

All URIs are relative to https://api.sodacards.com, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**publicAPIServiceGetBalance()**](PublicAPIServiceApi.md#publicAPIServiceGetBalance) | **GET** /v1/balance | GetBalance |


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
