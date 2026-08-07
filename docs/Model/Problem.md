# Problem

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**type** | **string** | A stable URI identifying the error kind; it resolves to the docs section for that code. |
**title** | **string** | A short, human-readable summary of the error kind. |
**status** | **int** | The HTTP status code, repeated in the body for convenience. |
**code** | **string** | The machine-readable reason (e.g. \&quot;insufficient_balance\&quot;): switch on this, never on the human text. |
**detail** | **string** | A human-readable explanation of this specific occurrence. May be absent. | [optional]
**request_id** | **string** | Identifies this request in support conversations. May be absent. | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
