# SodacardsDevpublicV1Product

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**id** | **string** | id identifies the product; use it to place an order for this item. | [optional]
**name** | **string** | name is the human-readable product name. | [optional]
**face_value** | [**\Sodacards\Model\SodacardsDevpublicV1ProductFaceValue**](SodacardsDevpublicV1ProductFaceValue.md) | face_value is the nominal value printed on the item (e.g. a 10 USD card),  which may differ from the currency the reseller pays in. | [optional]
**price** | [**\Sodacards\Model\SodacardsDevpublicV1Money**](SodacardsDevpublicV1Money.md) | price is what the reseller pays, in FCFA. It is absent when the item is not  yet priced (listed but not purchasable). | [optional]
**strike_price** | [**\Sodacards\Model\SodacardsDevpublicV1Money**](SodacardsDevpublicV1Money.md) | strike_price is an optional reference (pre-discount) price, in FCFA, for  display. Absent when there is none. | [optional]
**bonus** | **string** | bonus describes any extra value granted with the item, e.g. \&quot;+10%\&quot;. Empty  when there is none. | [optional]
**min_quantity** | **int** | min_quantity and max_quantity bound how many units an order line may buy. | [optional]
**max_quantity** | **int** |  | [optional]
**purchasable** | **bool** | purchasable is true when the item has a price and can be ordered now. | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
