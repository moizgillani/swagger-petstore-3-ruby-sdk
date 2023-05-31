# Pet

Everything about your Pets

Find out more: [http://swagger.io](http://swagger.io)

```ruby
pet_controller = client.pet
```

## Class Name

`PetController`

## Methods

* [Update Pet](../../doc/controllers/pet.md#update-pet)
* [Add Pet](../../doc/controllers/pet.md#add-pet)
* [Find Pets by Status](../../doc/controllers/pet.md#find-pets-by-status)
* [Find Pets by Tags](../../doc/controllers/pet.md#find-pets-by-tags)
* [Get Pet by Id](../../doc/controllers/pet.md#get-pet-by-id)
* [Update Pet With Form](../../doc/controllers/pet.md#update-pet-with-form)
* [Delete Pet](../../doc/controllers/pet.md#delete-pet)
* [Upload File](../../doc/controllers/pet.md#upload-file)


# Update Pet

Update an existing pet by Id

```ruby
def update_pet(name,
               photo_urls,
               id: nil,
               category: nil,
               tags: nil,
               pet_status: nil)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `name` | `String` | Form, Required | - |
| `photo_urls` | `Array<String>` | Form, Required | - |
| `id` | `Integer` | Form, Optional | - |
| `category` | [`Category`](../../doc/models/category.md) | Form, Optional | - |
| `tags` | [`Array<Tag>`](../../doc/models/tag.md) | Form, Optional | - |
| `pet_status` | [`PetStatusEnum`](../../doc/models/pet-status-enum.md) | Form, Optional | pet status in the store |

## Response Type

[`Pet`](../../doc/models/pet.md)

## Example Usage

```ruby
name = 'doggie'

photo_urls = [
  'photoUrls5',
  'photoUrls6',
  'photoUrls7'
]

id = 10

tags = [
  Tag.new(
    nil,
    nil
  )
]

result = pet_controller.update_pet(
  name,
  photo_urls,
  id: id,
  tags: tags
)
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Invalid ID supplied | `APIException` |
| 404 | Pet not found | `APIException` |
| 405 | Validation exception | `APIException` |


# Add Pet

Add a new pet to the store

```ruby
def add_pet(name,
            photo_urls,
            id: nil,
            category: nil,
            tags: nil,
            pet_status: nil)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `name` | `String` | Form, Required | - |
| `photo_urls` | `Array<String>` | Form, Required | - |
| `id` | `Integer` | Form, Optional | - |
| `category` | [`Category`](../../doc/models/category.md) | Form, Optional | - |
| `tags` | [`Array<Tag>`](../../doc/models/tag.md) | Form, Optional | - |
| `pet_status` | [`PetStatusEnum`](../../doc/models/pet-status-enum.md) | Form, Optional | pet status in the store |

## Response Type

[`Pet`](../../doc/models/pet.md)

## Example Usage

```ruby
name = 'doggie'

photo_urls = [
  'photoUrls5',
  'photoUrls6',
  'photoUrls7'
]

id = 10

tags = [
  Tag.new(
    nil,
    nil
  )
]

result = pet_controller.add_pet(
  name,
  photo_urls,
  id: id,
  tags: tags
)
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 405 | Invalid input | `APIException` |


# Find Pets by Status

Multiple status values can be provided with comma separated strings

```ruby
def find_pets_by_status(status: StatusEnum::AVAILABLE)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `status` | [`StatusEnum`](../../doc/models/status-enum.md) | Query, Optional | Status values that need to be considered for filter<br>**Default**: `StatusEnum::AVAILABLE` |

## Response Type

[`Array<Pet>`](../../doc/models/pet.md)

## Example Usage

```ruby
status = StatusEnum::AVAILABLE

result = pet_controller.find_pets_by_status(status: status)
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Invalid status value | `APIException` |


# Find Pets by Tags

Multiple tags can be provided with comma separated strings. Use tag1, tag2, tag3 for testing.

```ruby
def find_pets_by_tags(tags: nil)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `tags` | `Array<String>` | Query, Optional | Tags to filter by |

## Response Type

[`Array<Pet>`](../../doc/models/pet.md)

## Example Usage

```ruby
result = pet_controller.find_pets_by_tags
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Invalid tag value | `APIException` |


# Get Pet by Id

Returns a single pet

```ruby
def get_pet_by_id(pet_id)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `pet_id` | `Integer` | Template, Required | ID of pet to return |

## Response Type

[`Pet`](../../doc/models/pet.md)

## Example Usage

```ruby
pet_id = 152

result = pet_controller.get_pet_by_id(pet_id)
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Invalid ID supplied | `APIException` |
| 404 | Pet not found | `APIException` |


# Update Pet With Form

Updates a pet in the store with form data

```ruby
def update_pet_with_form(pet_id,
                         name: nil,
                         status: nil)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `pet_id` | `Integer` | Template, Required | ID of pet that needs to be updated |
| `name` | `String` | Query, Optional | Name of pet that needs to be updated |
| `status` | `String` | Query, Optional | Status of pet that needs to be updated |

## Response Type

`void`

## Example Usage

```ruby
pet_id = 152

pet_controller.update_pet_with_form(pet_id)
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 405 | Invalid input | `APIException` |


# Delete Pet

delete a pet

```ruby
def delete_pet(pet_id,
               api_key: nil)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `pet_id` | `Integer` | Template, Required | Pet id to delete |
| `api_key` | `String` | Header, Optional | - |

## Response Type

`void`

## Example Usage

```ruby
pet_id = 152

pet_controller.delete_pet(pet_id)
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Invalid pet value | `APIException` |


# Upload File

uploads an image

```ruby
def upload_file(pet_id,
                additional_metadata: nil,
                body: nil)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `pet_id` | `Integer` | Template, Required | ID of pet to update |
| `additional_metadata` | `String` | Query, Optional | Additional Metadata |
| `body` | `File \| UploadIO` | Form, Optional | - |

## Response Type

[`PetImage`](../../doc/models/pet-image.md)

## Example Usage

```ruby
pet_id = 152

result = pet_controller.upload_file(pet_id)
```

