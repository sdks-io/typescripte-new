# User

Operations about user

Find out more about our store: [http://swagger.io](http://swagger.io)

```ts
const userController = new UserController(client);
```

## Class Name

`UserController`

## Methods

* [Create Users With Array Input](../../doc/controllers/user.md#create-users-with-array-input)
* [Get User by Name](../../doc/controllers/user.md#get-user-by-name)
* [Delete User](../../doc/controllers/user.md#delete-user)
* [Login User](../../doc/controllers/user.md#login-user)
* [Create Users With List Input](../../doc/controllers/user.md#create-users-with-list-input)
* [Update User](../../doc/controllers/user.md#update-user)
* [Logout User](../../doc/controllers/user.md#logout-user)
* [Create User](../../doc/controllers/user.md#create-user)


# Create Users With Array Input

Creates list of users with given input array

```ts
async createUsersWithArrayInput(
  body: User[],
  requestOptions?: RequestOptions
): Promise<ApiResponse<void>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`User[]`](../../doc/models/user.md) | Body, Required | List of user object |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

`void`

## Example Usage

```ts
const body: User[] = [
  {}
];

try {
  const { result, ...httpResponse } = await userController.createUsersWithArrayInput(body);
  // Get more response info...
  // const { statusCode, headers } = httpResponse;
} catch (error) {
  if (error instanceof ApiError) {
    const errors = error.result;
    // const { statusCode, headers } = error;
  }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | successful operation | `ApiError` |


# Get User by Name

Get user by user name

```ts
async getUserByName(
  username: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<User>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `username` | `string` | Template, Required | The name that needs to be fetched. Use user1 for testing. |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

[`User`](../../doc/models/user.md)

## Example Usage

```ts
const username = 'username0';

try {
  const { result, ...httpResponse } = await userController.getUserByName(username);
  // Get more response info...
  // const { statusCode, headers } = httpResponse;
} catch (error) {
  if (error instanceof ApiError) {
    const errors = error.result;
    // const { statusCode, headers } = error;
  }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Invalid username supplied | `ApiError` |
| 404 | User not found | `ApiError` |


# Delete User

This can only be done by the logged in user.

```ts
async deleteUser(
  username: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<void>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `username` | `string` | Template, Required | The name that needs to be deleted |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

`void`

## Example Usage

```ts
const username = 'username0';

try {
  const { result, ...httpResponse } = await userController.deleteUser(username);
  // Get more response info...
  // const { statusCode, headers } = httpResponse;
} catch (error) {
  if (error instanceof ApiError) {
    const errors = error.result;
    // const { statusCode, headers } = error;
  }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Invalid username supplied | `ApiError` |
| 404 | User not found | `ApiError` |


# Login User

Logs user into the system

```ts
async loginUser(
  username: string,
  password: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<string>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `username` | `string` | Query, Required | The user name for login |
| `password` | `string` | Query, Required | The password for login in clear text |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

`string`

## Example Usage

```ts
const username = 'username0';

const password = 'password4';

try {
  const { result, ...httpResponse } = await userController.loginUser(
    username,
    password
  );
  // Get more response info...
  // const { statusCode, headers } = httpResponse;
} catch (error) {
  if (error instanceof ApiError) {
    const errors = error.result;
    // const { statusCode, headers } = error;
  }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Invalid username/password supplied | `ApiError` |


# Create Users With List Input

Creates list of users with given input array

```ts
async createUsersWithListInput(
  body: User[],
  requestOptions?: RequestOptions
): Promise<ApiResponse<void>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`User[]`](../../doc/models/user.md) | Body, Required | List of user object |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

`void`

## Example Usage

```ts
const body: User[] = [
  {}
];

try {
  const { result, ...httpResponse } = await userController.createUsersWithListInput(body);
  // Get more response info...
  // const { statusCode, headers } = httpResponse;
} catch (error) {
  if (error instanceof ApiError) {
    const errors = error.result;
    // const { statusCode, headers } = error;
  }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | successful operation | `ApiError` |


# Update User

This can only be done by the logged in user.

```ts
async updateUser(
  username: string,
  body: User,
  requestOptions?: RequestOptions
): Promise<ApiResponse<void>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `username` | `string` | Template, Required | name that need to be updated |
| `body` | [`User`](../../doc/models/user.md) | Body, Required | Updated user object |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

`void`

## Example Usage

```ts
const username = 'username0';

const body: User = {};

try {
  const { result, ...httpResponse } = await userController.updateUser(
    username,
    body
  );
  // Get more response info...
  // const { statusCode, headers } = httpResponse;
} catch (error) {
  if (error instanceof ApiError) {
    const errors = error.result;
    // const { statusCode, headers } = error;
  }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Invalid user supplied | `ApiError` |
| 404 | User not found | `ApiError` |


# Logout User

Logs out current logged in user session

```ts
async logoutUser(
  requestOptions?: RequestOptions
): Promise<ApiResponse<void>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

`void`

## Example Usage

```ts
try {
  const { result, ...httpResponse } = await userController.logoutUser();
  // Get more response info...
  // const { statusCode, headers } = httpResponse;
} catch (error) {
  if (error instanceof ApiError) {
    const errors = error.result;
    // const { statusCode, headers } = error;
  }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | successful operation | `ApiError` |


# Create User

This can only be done by the logged in user.

```ts
async createUser(
  body: User,
  requestOptions?: RequestOptions
): Promise<ApiResponse<void>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`User`](../../doc/models/user.md) | Body, Required | Created user object |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

`void`

## Example Usage

```ts
const body: User = {};

try {
  const { result, ...httpResponse } = await userController.createUser(body);
  // Get more response info...
  // const { statusCode, headers } = httpResponse;
} catch (error) {
  if (error instanceof ApiError) {
    const errors = error.result;
    // const { statusCode, headers } = error;
  }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | successful operation | `ApiError` |

