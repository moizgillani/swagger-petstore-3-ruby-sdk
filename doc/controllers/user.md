# User

Operations about user

```ruby
user_controller = client.user
```

## Class Name

`UserController`

## Methods

* [Create User](../../doc/controllers/user.md#create-user)
* [Create Users With List Input](../../doc/controllers/user.md#create-users-with-list-input)
* [Login User](../../doc/controllers/user.md#login-user)
* [Logout User](../../doc/controllers/user.md#logout-user)
* [Get User by Name](../../doc/controllers/user.md#get-user-by-name)
* [Update User](../../doc/controllers/user.md#update-user)
* [Delete User](../../doc/controllers/user.md#delete-user)


# Create User

This can only be done by the logged in user.

```ruby
def create_user(id: nil,
                username: nil,
                first_name: nil,
                last_name: nil,
                email: nil,
                password: nil,
                phone: nil,
                user_status: nil)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `Integer` | Form, Optional | - |
| `username` | `String` | Form, Optional | - |
| `first_name` | `String` | Form, Optional | - |
| `last_name` | `String` | Form, Optional | - |
| `email` | `String` | Form, Optional | - |
| `password` | `String` | Form, Optional | - |
| `phone` | `String` | Form, Optional | - |
| `user_status` | `Integer` | Form, Optional | User Status |

## Response Type

[`User`](../../doc/models/user.md)

## Example Usage

```ruby
id = 10

username = 'theUser'

first_name = 'John'

last_name = 'James'

email = 'john@email.com'

password = '12345'

phone = '12345'

user_status = 1

result = user_controller.create_user(
  id: id,
  username: username,
  first_name: first_name,
  last_name: last_name,
  email: email,
  password: password,
  phone: phone,
  user_status: user_status
)
```


# Create Users With List Input

Creates list of users with given input array

```ruby
def create_users_with_list_input(body: nil)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`Array<User>`](../../doc/models/user.md) | Body, Optional | - |

## Response Type

[`User`](../../doc/models/user.md)

## Example Usage

```ruby
result = user_controller.create_users_with_list_input
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | successful operation | `APIException` |


# Login User

Logs user into the system

```ruby
def login_user(username: nil,
               password: nil)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `username` | `String` | Query, Optional | The user name for login |
| `password` | `String` | Query, Optional | The password for login in clear text |

## Response Type

`String`

## Example Usage

```ruby
result = user_controller.login_user
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Invalid username/password supplied | `APIException` |


# Logout User

Logs out current logged in user session

```ruby
def logout_user
```

## Response Type

`void`

## Example Usage

```ruby
user_controller.logout_user
```


# Get User by Name

Get user by user name

```ruby
def get_user_by_name(name)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `name` | `String` | Template, Required | The name that needs to be fetched. Use user1 for testing. |

## Response Type

[`User`](../../doc/models/user.md)

## Example Usage

```ruby
name = 'name0'

result = user_controller.get_user_by_name(name)
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Invalid username supplied | `APIException` |
| 404 | User not found | `APIException` |


# Update User

This can only be done by the logged in user.

```ruby
def update_user(name,
                id: nil,
                username: nil,
                first_name: nil,
                last_name: nil,
                email: nil,
                password: nil,
                phone: nil,
                user_status: nil)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `name` | `String` | Template, Required | name that need to be deleted |
| `id` | `Integer` | Form, Optional | - |
| `username` | `String` | Form, Optional | - |
| `first_name` | `String` | Form, Optional | - |
| `last_name` | `String` | Form, Optional | - |
| `email` | `String` | Form, Optional | - |
| `password` | `String` | Form, Optional | - |
| `phone` | `String` | Form, Optional | - |
| `user_status` | `Integer` | Form, Optional | User Status |

## Response Type

`void`

## Example Usage

```ruby
name = 'name0'

id = 10

username = 'theUser'

first_name = 'John'

last_name = 'James'

email = 'john@email.com'

password = '12345'

phone = '12345'

user_status = 1

user_controller.update_user(
  name,
  id: id,
  username: username,
  first_name: first_name,
  last_name: last_name,
  email: email,
  password: password,
  phone: phone,
  user_status: user_status
)
```


# Delete User

This can only be done by the logged in user.

```ruby
def delete_user(name)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `name` | `String` | Template, Required | The name that needs to be deleted |

## Response Type

`void`

## Example Usage

```ruby
name = 'name0'

user_controller.delete_user(name)
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Invalid username supplied | `APIException` |
| 404 | User not found | `APIException` |

