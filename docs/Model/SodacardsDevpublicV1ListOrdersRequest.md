# SodacardsDevpublicV1ListOrdersRequest

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**limit** | **int** | limit is the maximum number of orders to return (1..100). Zero applies the  default page size. | [optional]
**cursor** | **string** | cursor is the next_cursor of the previous page. Empty for the first page. | [optional]
**reference** | **string** | reference, when set, filters the list to the orders carrying that client  reference. The cursor is ignored when a reference is given. | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
