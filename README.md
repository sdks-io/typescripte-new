
# Getting Started with Swagger Petstore

## Introduction

This is a sample server Petstore server.  You can find out more about Swagger at [http://swagger.io](http://swagger.io) or on [irc.freenode.net, #swagger](http://swagger.io/irc/).  For this sample, you can use the api key `special-key` to test the authorization filters.

Find out more about Swagger: [http://swagger.io](http://swagger.io)

## Install the Package

Run the following command from your project directory to install the package from npm:

```ts
npm install repo-test-sdk@2.3.363
```

For additional package details, see the [Npm page for the repo-test-sdk@2.3.363  npm](https://www.npmjs.com/package/repo-test-sdk/v/2.3.363).

## Initialize the API Client

**_Note:_** Documentation for the client can be found [here.](https://www.github.com/sdks-io/typescripte-new/tree/2.3.363/doc/client.md)

The following parameters are configurable for the API Client:

| Parameter | Type | Description |
|  --- | --- | --- |
| `environment` | Environment | The API environment. <br> **Default: `Environment.Production`** |
| `timeout` | `number` | Timeout for API calls.<br>*Default*: `0` |
| `httpClientOptions` | `Partial<HttpClientOptions>` | Stable configurable http client options. |
| `unstableHttpClientOptions` | `any` | Unstable configurable http client options. |
| `password` | `string` |  |

### HttpClientOptions

| Parameter | Type | Description |
|  --- | --- | --- |
| `timeout` | `number` | Timeout in milliseconds. |
| `httpAgent` | `any` | Custom http agent to be used when performing http requests. |
| `httpsAgent` | `any` | Custom https agent to be used when performing http requests. |
| `retryConfig` | `Partial<RetryConfiguration>` | Configurations to retry requests. |

### RetryConfiguration

| Parameter | Type | Description |
|  --- | --- | --- |
| `maxNumberOfRetries` | `number` | Maximum number of retries. <br> *Default*: `0` |
| `retryOnTimeout` | `boolean` | Whether to retry on request timeout. <br> *Default*: `true` |
| `retryInterval` | `number` | Interval before next retry. Used in calculation of wait time for next request in case of failure. <br> *Default*: `1` |
| `maximumRetryWaitTime` | `number` | Overall wait time for the requests getting retried. <br> *Default*: `0` |
| `backoffFactor` | `number` | Used in calculation of wait time for next request in case of failure. <br> *Default*: `2` |
| `httpStatusCodesToRetry` | `number[]` | Http status codes to retry against. <br> *Default*: `[408, 413, 429, 500, 502, 503, 504, 521, 522, 524]` |
| `httpMethodsToRetry` | `HttpMethod[]` | Http methods to retry against. <br> *Default*: `['GET', 'PUT']` |

The API client can be initialized as follows:

```ts
const client = new Client({
  timeout: 0,
  environment: Environment.Production,
  password: 'Password',
});
```

## Authorization

This API uses `Custom Authentication`.

## List of APIs

* [Pet](https://www.github.com/sdks-io/typescripte-new/tree/2.3.363/doc/controllers/pet.md)
* [Store](https://www.github.com/sdks-io/typescripte-new/tree/2.3.363/doc/controllers/store.md)
* [User](https://www.github.com/sdks-io/typescripte-new/tree/2.3.363/doc/controllers/user.md)

## Classes Documentation

* [ApiResponse](https://www.github.com/sdks-io/typescripte-new/tree/2.3.363/doc/api-response.md)
* [ApiError](https://www.github.com/sdks-io/typescripte-new/tree/2.3.363/doc/api-error.md)

