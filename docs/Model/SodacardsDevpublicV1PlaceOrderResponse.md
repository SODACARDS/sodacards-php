# SodacardsDevpublicV1PlaceOrderResponse

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**order** | [**\Sodacards\Model\SodacardsDevpublicV1PlacedOrder**](SodacardsDevpublicV1PlacedOrder.md) | order is the accepted order. It is settled from the wallet at placement, so it  is born already paid: its status is \&quot;processing\&quot; while it is being fulfilled,  or \&quot;completed\&quot; when fulfillment is immediate. It is never \&quot;pending\&quot; -- the  developer API charges synchronously, so an order awaiting payment is not a  state it produces. Poll the order to follow it to \&quot;completed\&quot;. | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
