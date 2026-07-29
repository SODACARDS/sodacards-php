# SodacardsDevpublicV1OrderItem

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**product_id** | **string** | product_id is the product ordered on this line. | [optional]
**name** | **string** | name is the product name at order time. | [optional]
**unit_price** | [**\Sodacards\Model\SodacardsDevpublicV1Money**](SodacardsDevpublicV1Money.md) | unit_price is the price of one unit, in the currency of Money. | [optional]
**quantity** | **int** | quantity is how many units were ordered. | [optional]
**line_total** | [**\Sodacards\Model\SodacardsDevpublicV1Money**](SodacardsDevpublicV1Money.md) | line_total is unit_price times quantity, in the currency of Money. | [optional]
**input_fields** | **array<string,string>** | input_fields are the purchase-form values submitted for this line. | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
