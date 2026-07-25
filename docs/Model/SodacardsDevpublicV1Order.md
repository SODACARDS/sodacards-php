# SodacardsDevpublicV1Order

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**id** | **string** | id identifies the order. | [optional]
**status** | **string** | status is the order&#39;s current state: \&quot;pending\&quot;, \&quot;processing\&quot;, \&quot;completed\&quot;,  \&quot;failed\&quot; or \&quot;refunded\&quot;. | [optional]
**total** | [**\Sodacards\Model\SodacardsDevpublicV1Money**](SodacardsDevpublicV1Money.md) | total is the amount charged for the order, in FCFA. | [optional]
**created_at** | **string** | created_at is when the order was placed (RFC 3339). | [optional]
**reference** | **string** | reference is the identifier you attached at creation, empty if none. | [optional]
**lines** | [**\Sodacards\Model\SodacardsDevpublicV1OrderItem[]**](SodacardsDevpublicV1OrderItem.md) | lines are the ordered products. | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
