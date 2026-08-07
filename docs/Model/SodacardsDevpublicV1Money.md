# SodacardsDevpublicV1Money

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**amount** | [**\Sodacards\Model\Amount**](Amount.md) |  | [optional]
**currency** | **string** | currency is the ISO-4217 code, e.g. \&quot;XOF\&quot;. | [optional]
**minor_unit_exponent** | **int** | minor_unit_exponent is the currency&#39;s number of decimal places (0 for XOF,  2 for USD): amount divided by 10^minor_unit_exponent is the major-unit value.  The example is 0 on purpose: XOF has no minor unit, and an explicit example  keeps the field visible in the docs even though its value is a zero. | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
