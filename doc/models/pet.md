
# Pet

## Structure

`Pet`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `name` | `String` | Required | - |
| `photo_urls` | `Array<String>` | Required | - |
| `id` | `Integer` | Optional | - |
| `category` | [`Category`](../../doc/models/category.md) | Optional | - |
| `tags` | [`Array<Tag>`](../../doc/models/tag.md) | Optional | - |
| `pet_status` | [`PetStatusEnum`](../../doc/models/pet-status-enum.md) | Optional | pet status in the store |

## Example (as JSON)

```json
{
  "name": "doggie",
  "photoUrls": [
    "photoUrls5",
    "photoUrls6",
    "photoUrls7"
  ],
  "id": 10,
  "category": {
    "id": 232,
    "name": "name2"
  },
  "tags": [
    {
      "id": 239,
      "name": "name5"
    },
    {
      "id": 240,
      "name": "name6"
    }
  ],
  "petStatus": "pending"
}
```

