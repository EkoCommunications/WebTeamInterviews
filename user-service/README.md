# User service spec

The user service is a simple CRUD + Query micro service which handles the pool of users of a customer's application.

The specs below have been created by the backend team after a product scoping session, and it's now time to review these specs for integration inside the web sdk.

## Models

```ts
type UserModel = {
    userId: string // primary key in db
    displayName: string
    tags: string[]
    createdAt: Date
    updatedAt: Date
}
```

<br>

## Endpoints

### Create a user

- Method: `POST`
- Path: `/user`
- Querystring:
  ```
  ```
- Body:
  ```ts
  type CreatePayload = {
    userId: string
    displayName?: string
    tags?: string[]
  }
  ```
- Returns: `UserModel`

---

### Get one user

- Method: `GET`
- Path: `/users/:userId`
- Querystring:
  ```
  ```
- Body:
  ```
  ```
- Returns: `UserModel`

---

### Get many users

- Method: `GET`
- Path: `/users/`
- Querystring:
  ```
  ```
- Body:
  ```ts
  type GetManyPayload = {
    userIds: string[]
  }
  ```
- Returns: `UserModel[]`

---

### Query users

- Method: `GET`
- Path: `/users/`
- Querystring:
  ```
  ```
- Body:
  ```ts
  type QueryPayload = {
    withTags?: string[]
    skip?: number
    limit?: number
  }
  ```
- Returns: `UserModel[]`

---

### Update a user

- Method: `PUT`
- Path: `/users/`
- Querystring:
  ```
  ```
- Body:
  ```ts
  type UpdatePayload = {
    userId: string
    displayName?: string
    tags?: string[]
  }
  ```
- Returns: `UserModel`

---

### Delete a user

- Method: `DELETE`
- Path: `/users/`
- Querystring:
  ```ts
  type DeletePayload = {
    userId: string
  }
  ```
- Body:
  ```
  ```
- Returns:** `boolean`