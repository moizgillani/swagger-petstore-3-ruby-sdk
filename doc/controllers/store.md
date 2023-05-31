# Store

Access to Petstore orders

Find out more about our store: [http://swagger.io](http://swagger.io)

```ruby
store_controller = client.store
```

## Class Name

`StoreController`

## Methods

* [Get Inventory](../../doc/controllers/store.md#get-inventory)
* [Place Order](../../doc/controllers/store.md#place-order)
* [Get Order by Id](../../doc/controllers/store.md#get-order-by-id)
* [Delete Order](../../doc/controllers/store.md#delete-order)


# Get Inventory

Returns a map of status codes to quantities

```ruby
def get_inventory
```

## Response Type

`Hash of Integer`

## Example Usage

```ruby
result = store_controller.get_inventory
```


# Place Order

Place a new order in the store

```ruby
def place_order(id: nil,
                pet_id: nil,
                quantity: nil,
                ship_date: nil,
                order_status: OrderStatusEnum::APPROVED,
                complete: nil)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `Integer` | Form, Optional | - |
| `pet_id` | `Integer` | Form, Optional | - |
| `quantity` | `Integer` | Form, Optional | - |
| `ship_date` | `DateTime` | Form, Optional | - |
| `order_status` | [`OrderStatusEnum`](../../doc/models/order-status-enum.md) | Form, Optional | Order Status<br>**Default**: `OrderStatusEnum::APPROVED` |
| `complete` | `TrueClass\|FalseClass` | Form, Optional | - |

## Response Type

[`Order`](../../doc/models/order.md)

## Example Usage

```ruby
id = 10

pet_id = 198772

quantity = 7

ship_date = DateTimeHelper.from_rfc3339('05/31/2023 00:00:00')

order_status = OrderStatusEnum::APPROVED

complete = true

result = store_controller.place_order(
  id: id,
  pet_id: pet_id,
  quantity: quantity,
  ship_date: ship_date,
  order_status: order_status,
  complete: complete
)
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 405 | Invalid input | `APIException` |


# Get Order by Id

For valid response try integer IDs with value <= 5 or > 10. Other values will generate exceptions.

```ruby
def get_order_by_id(order_id)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `order_id` | `Integer` | Template, Required | ID of order that needs to be fetched |

## Response Type

[`Order`](../../doc/models/order.md)

## Example Usage

```ruby
order_id = 62

result = store_controller.get_order_by_id(order_id)
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Invalid ID supplied | `APIException` |
| 404 | Order not found | `APIException` |


# Delete Order

For valid response try integer IDs with value < 1000. Anything above 1000 or nonintegers will generate API errors

```ruby
def delete_order(order_id)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `order_id` | `Integer` | Template, Required | ID of the order that needs to be deleted |

## Response Type

`void`

## Example Usage

```ruby
order_id = 62

store_controller.delete_order(order_id)
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Invalid ID supplied | `APIException` |
| 404 | Order not found | `APIException` |

