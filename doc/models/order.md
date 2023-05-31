
# Order

## Structure

`Order`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `Integer` | Optional | - |
| `pet_id` | `Integer` | Optional | - |
| `quantity` | `Integer` | Optional | - |
| `ship_date` | `DateTime` | Optional | - |
| `order_status` | [`OrderStatusEnum`](../../doc/models/order-status-enum.md) | Optional | Order Status<br>**Default**: `OrderStatusEnum::APPROVED` |
| `complete` | `TrueClass\|FalseClass` | Optional | - |

## Example (as JSON)

```json
{
  "id": 10,
  "petId": 198772,
  "quantity": 7,
  "shipDate": "05/31/2023 00:00:00",
  "orderStatus": "approved",
  "complete": true
}
```

