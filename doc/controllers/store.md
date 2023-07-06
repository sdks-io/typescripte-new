# Store

Access to Petstore orders

```ts
const storeController = new StoreController(client);
```

## Class Name

`StoreController`

## Methods

* [Place Order](../../doc/controllers/store.md#place-order)
* [Get Order by Id](../../doc/controllers/store.md#get-order-by-id)
* [Delete Order](../../doc/controllers/store.md#delete-order)
* [Get Inventory](../../doc/controllers/store.md#get-inventory)


# Place Order

Place an order for a pet

```ts
async placeOrder(
  body: Order,
  requestOptions?: RequestOptions
): Promise<ApiResponse<Order>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`Order`](../../doc/models/order.md) | Body, Required | order placed for purchasing the pet |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

[`Order`](../../doc/models/order.md)

## Example Usage

```ts
const body: Order = {};

try {
  const { result, ...httpResponse } = await storeController.placeOrder(body);
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
| 400 | Invalid Order | `ApiError` |


# Get Order by Id

For valid response try integer IDs with value >= 1 and <= 10. Other values will generated exceptions

```ts
async getOrderById(
  orderId: bigint,
  requestOptions?: RequestOptions
): Promise<ApiResponse<Order>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `orderId` | `bigint` | Template, Required | ID of pet that needs to be fetched<br>**Constraints**: `>= 1`, `<= 10` |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

[`Order`](../../doc/models/order.md)

## Example Usage

```ts
const orderId = BigInt(62);

try {
  const { result, ...httpResponse } = await storeController.getOrderById(orderId);
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
| 400 | Invalid ID supplied | `ApiError` |
| 404 | Order not found | `ApiError` |


# Delete Order

For valid response try integer IDs with positive integer value. Negative or non-integer values will generate API errors

```ts
async deleteOrder(
  orderId: bigint,
  requestOptions?: RequestOptions
): Promise<ApiResponse<void>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `orderId` | `bigint` | Template, Required | ID of the order that needs to be deleted<br>**Constraints**: `>= 1` |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

`void`

## Example Usage

```ts
const orderId = BigInt(62);

try {
  const { result, ...httpResponse } = await storeController.deleteOrder(orderId);
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
| 400 | Invalid ID supplied | `ApiError` |
| 404 | Order not found | `ApiError` |


# Get Inventory

Returns a map of status codes to quantities

```ts
async getInventory(
  requestOptions?: RequestOptions
): Promise<ApiResponse<Record<string, number>>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

`Record<string, number>`

## Example Usage

```ts
try {
  const { result, ...httpResponse } = await storeController.getInventory();
  // Get more response info...
  // const { statusCode, headers } = httpResponse;
} catch (error) {
  if (error instanceof ApiError) {
    const errors = error.result;
    // const { statusCode, headers } = error;
  }
}
```

