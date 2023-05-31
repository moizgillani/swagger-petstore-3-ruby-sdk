
# Customer

## Structure

`Customer`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `Integer` | Optional | - |
| `username` | `String` | Optional | - |
| `address` | [`Array<Address>`](../../doc/models/address.md) | Optional | - |

## Example (as JSON)

```json
{
  "id": 100000,
  "username": "fehguy",
  "address": [
    {
      "street": "street4",
      "city": "city4",
      "state": "state0",
      "zip": "zip8"
    }
  ]
}
```

