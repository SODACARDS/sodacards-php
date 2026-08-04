# SodacardsDevpublicV1InputFieldSpec

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**key** | **string** | key is the field&#39;s machine name and the key to use in  OrderLine.input_fields, e.g. \&quot;player_id\&quot;. | [optional]
**type** | **string** | type is how to render and validate the value: \&quot;text\&quot;, \&quot;number\&quot; or \&quot;select\&quot;. | [optional]
**required** | **bool** | required is true when an order line for this product must carry this field. | [optional]
**regex** | **string** | regex, when present, is a regular expression the submitted value must match  (text and number fields). Empty when there is no pattern constraint. | [optional]
**options** | [**\Sodacards\Model\SodacardsDevpublicV1InputFieldOption[]**](SodacardsDevpublicV1InputFieldOption.md) | options are the allowed values of a \&quot;select\&quot; field, in display order. Empty  for text and number fields. | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
