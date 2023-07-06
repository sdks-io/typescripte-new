# Pet

Everything about your Pets

Find out more: [http://swagger.io](http://swagger.io)

```ts
const petController = new PetController(client);
```

## Class Name

`PetController`

## Methods

* [Upload File](../../doc/controllers/pet.md#upload-file)
* [Inpet](../../doc/controllers/pet.md#inpet)
* [Update an Pet](../../doc/controllers/pet.md#update-an-pet)
* [Find Pet in the Status](../../doc/controllers/pet.md#find-pet-in-the-status)
* [Find Pets an Tags](../../doc/controllers/pet.md#find-pets-an-tags)
* [Get Pet by Id](../../doc/controllers/pet.md#get-pet-by-id)
* [Update Pet With Form](../../doc/controllers/pet.md#update-pet-with-form)
* [Delete Pet](../../doc/controllers/pet.md#delete-pet)


# Upload File

uploads an image

```ts
async uploadFile(
  petId: bigint,
  additionalMetadata?: string,
  file?: FileWrapper,
  requestOptions?: RequestOptions
): Promise<ApiResponse<MApiResponse>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `petId` | `bigint` | Template, Required | ID of pet to update |
| `additionalMetadata` | `string \| undefined` | Form, Optional | Additional data to pass to server |
| `file` | `FileWrapper \| undefined` | Form, Optional | file to upload |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

[`MApiResponse`](../../doc/models/m-api-response.md)

## Example Usage

```ts
const petId = BigInt(152);

try {
  const { result, ...httpResponse } = await petController.uploadFile(petId);
  // Get more response info...
  // const { statusCode, headers } = httpResponse;
} catch (error) {
  if (error instanceof ApiError) {
    const errors = error.result;
    // const { statusCode, headers } = error;
  }
}
```


# Inpet

Add a new pet to the store

```ts
async inpet(
  body: Pet,
  requestOptions?: RequestOptions
): Promise<ApiResponse<void>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`Pet`](../../doc/models/pet.md) | Body, Required | Pet object that needs to be added to the store |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

`void`

## Example Usage

```ts
const body: Pet = {
  name: 'name6',
  photoUrls: [
    'photoUrls1'
  ],
};

try {
  const { result, ...httpResponse } = await petController.inpet(body);
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
| 405 | Invalid input | `ApiError` |


# Update an Pet

Update an existing pet

```ts
async updateAnPet(
  body: Pet,
  requestOptions?: RequestOptions
): Promise<ApiResponse<void>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`Pet`](../../doc/models/pet.md) | Body, Required | Pet object that needs to be added to the store |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

`void`

## Example Usage

```ts
const body: Pet = {
  name: 'name6',
  photoUrls: [
    'photoUrls1'
  ],
};

try {
  const { result, ...httpResponse } = await petController.updateAnPet(body);
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
| 404 | Pet not found | `ApiError` |
| 405 | Validation exception | `ApiError` |


# Find Pet in the Status

Multiple status values can be provided with comma separated strings

```ts
async findPetInTheStatus(
  status: Status2Enum[],
  requestOptions?: RequestOptions
): Promise<ApiResponse<Pet[]>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `status` | [`Status2Enum[]`](../../doc/models/status-2-enum.md) | Query, Required | Status values that need to be considered for filter |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

[`Pet[]`](../../doc/models/pet.md)

## Example Usage

```ts
const status: Status2Enum[] = [
  Status2Enum.Pending,
  Status2Enum.Sold,
  Status2Enum.Available
];

try {
  const { result, ...httpResponse } = await petController.findPetInTheStatus(status);
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
| 400 | Invalid status value | `ApiError` |


# Find Pets an Tags

**This endpoint is deprecated.**

Multiple tags can be provided with comma separated strings. Use tag1, tag2, tag3 for testing.

```ts
async findPetsAnTags(
  tags: string[],
  requestOptions?: RequestOptions
): Promise<ApiResponse<Pet[]>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `tags` | `string[]` | Query, Required | Tags to filter by |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

[`Pet[]`](../../doc/models/pet.md)

## Example Usage

```ts
const tags: string[] = [
  'tags5',
  'tags6'
];

try {
  const { result, ...httpResponse } = await petController.findPetsAnTags(tags);
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
| 400 | Invalid tag value | `ApiError` |


# Get Pet by Id

Returns a single pet

```ts
async getPetById(
  petId: bigint,
  requestOptions?: RequestOptions
): Promise<ApiResponse<Pet>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `petId` | `bigint` | Template, Required | ID of pet to return |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

[`Pet`](../../doc/models/pet.md)

## Example Usage

```ts
const petId = BigInt(152);

try {
  const { result, ...httpResponse } = await petController.getPetById(petId);
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
| 404 | Pet not found | `ApiError` |


# Update Pet With Form

Updates a pet in the store with form data

```ts
async updatePetWithForm(
  petId: bigint,
  name?: string,
  status?: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<void>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `petId` | `bigint` | Template, Required | ID of pet that needs to be updated |
| `name` | `string \| undefined` | Form, Optional | Updated name of the pet |
| `status` | `string \| undefined` | Form, Optional | Updated status of the pet |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

`void`

## Example Usage

```ts
const petId = BigInt(152);

try {
  const { result, ...httpResponse } = await petController.updatePetWithForm(petId);
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
| 405 | Invalid input | `ApiError` |


# Delete Pet

Deletes a pet

```ts
async deletePet(
  petId: bigint,
  apiKey?: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<void>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `petId` | `bigint` | Template, Required | Pet id to delete |
| `apiKey` | `string \| undefined` | Header, Optional | - |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

`void`

## Example Usage

```ts
const petId = BigInt(152);

try {
  const { result, ...httpResponse } = await petController.deletePet(petId);
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
| 404 | Pet not found | `ApiError` |

