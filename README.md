
# Getting Started with Swagger Petstore - OpenAPI 3.0

## Introduction

This is a sample Pet Store Server based on the OpenAPI 3.0 specification.  You can find out more about
Swagger at [https://swagger.io](https://swagger.io). In the third iteration of the pet store, we've switched to the design first approach!
You can now help us improve the API whether it's by making changes to the definition itself or to the code.
That way, with time, we can improve the API in general, and expose some of the new features in OAS3.

_If you're looking for the Swagger 2.0/OAS 2.0 version of Petstore, then click [here](https://editor.swagger.io/?url=https://petstore.swagger.io/v2/swagger.yaml). Alternatively, you can load via the `Edit > Load Petstore OAS 2.0` menu option!_

Some useful links:

- [The Pet Store repository](https://github.com/swagger-api/swagger-petstore)
- [The source API definition for the Pet Store](https://github.com/swagger-api/swagger-petstore/blob/master/src/main/resources/openapi.yaml)

Find out more about Swagger: [http://swagger.io](http://swagger.io)

## Install the Package

Install the gem from the command line:

```ruby
gem install swagger-petstore-3-sdk -v 1.0.4
```

Or add the gem to your Gemfile and run `bundle`:

```ruby
gem 'swagger-petstore-3-sdk', '1.0.4'
```

For additional gem details, see the [RubyGems page for the swagger-petstore-3-sdk gem](https://rubygems.org/gems/swagger-petstore-3-sdk/versions/1.0.4).

## Test the SDK

To run the tests, navigate to the root directory of the SDK in your terminal and execute the following command:

```
rake
```

## Initialize the API Client

**_Note:_** Documentation for the client can be found [here.](https://www.github.com/moizgillani/swagger-petstore-3-ruby-sdk/tree/1.0.4/doc/client.md)

The following parameters are configurable for the API Client:

| Parameter | Type | Description |
|  --- | --- | --- |
| `connection` | `Faraday::Connection` | The Faraday connection object passed by the SDK user for making requests |
| `adapter` | `Faraday::Adapter` | The Faraday adapter object passed by the SDK user for performing http requests |
| `timeout` | `Float` | The value to use for connection timeout. <br> **Default: 60** |
| `max_retries` | `Integer` | The number of times to retry an endpoint call if it fails. <br> **Default: 0** |
| `retry_interval` | `Float` | Pause in seconds between retries. <br> **Default: 1** |
| `backoff_factor` | `Float` | The amount to multiply each successive retry's interval amount by in order to provide backoff. <br> **Default: 2** |
| `retry_statuses` | `Array` | A list of HTTP statuses to retry. <br> **Default: [408, 413, 429, 500, 502, 503, 504, 521, 522, 524]** |
| `retry_methods` | `Array` | A list of HTTP methods to retry. <br> **Default: %i[get put]** |
| `http_callback` | `HttpCallBack` | The Http CallBack allows defining callables for pre and post API calls. |
| `api_key` | `String` |  |

The API client can be initialized as follows:

```ruby
client = SwaggerPetstoreOpenApi30::Client.new(
  api_key: 'api_key'
)
```

## Authorization

This API uses `Custom Header Signature`.

## List of APIs

* [Pet](https://www.github.com/moizgillani/swagger-petstore-3-ruby-sdk/tree/1.0.4/doc/controllers/pet.md)
* [Store](https://www.github.com/moizgillani/swagger-petstore-3-ruby-sdk/tree/1.0.4/doc/controllers/store.md)
* [User](https://www.github.com/moizgillani/swagger-petstore-3-ruby-sdk/tree/1.0.4/doc/controllers/user.md)

## Classes Documentation

* [Utility Classes](https://www.github.com/moizgillani/swagger-petstore-3-ruby-sdk/tree/1.0.4/doc/utility-classes.md)
* [HttpResponse](https://www.github.com/moizgillani/swagger-petstore-3-ruby-sdk/tree/1.0.4/doc/http-response.md)
* [HttpRequest](https://www.github.com/moizgillani/swagger-petstore-3-ruby-sdk/tree/1.0.4/doc/http-request.md)

