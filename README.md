# Spammer API Documentation

`export const API = "https://spammer-backend.onrender.com"`

## GET /messages

### Request:

```js
fetch(`${API}/messages`);
```

### Response:

```js
{
"success": true,
"messages": [{...}, {...}, {...}]
}
```

## POST /messages

### Request:

```js
fetch(`${API}/messages`, {
  method: "POST",
  headers: {
    "Content-Type": "application/json",
  },
  body: JSON.stringify({
    text: "Hi",
    parentId: "caa490bf-d915-4419-86d0-e6fe95c74239",
  }),
});
```

### Response:

```js
{
  "success": true,
  "message": {
    "id": "b52c4655-3cde-489f-aa93-7869bcc0a802",
    "createdAt": "2023-07-09T16:40:33.447Z",
    "text": "hi",
    "parentId": "caa490bf-d915-4419-86d0-e6fe95c74239",
    "likes": 0
  }
}
```

## PUT /message/:messageId

### Request:

```js
fetch(`${API}/message/b52c4655-3cde-489f-aa93-7869bcc0a802`, {
  method: "PUT",
  headers: {
    "Content-Type": "application/json",
  },
  body: JSON.stringify({ text: "Hi2", likes: 10 }),
});
```

### Response:

```js
{
  "success": true,
  "message": {
    "id": "b52c4655-3cde-489f-aa93-7869bcc0a802",
    "createdAt": "2023-07-09T16:40:33.447Z",
    "text": "hi2",
    "parentId": "caa490bf-d915-4419-86d0-e6fe95c74239",
    "likes": 10
  }
}
```

## DELETE /message/:messageId

### Request:

```js
fetch(`${API}/message/b52c4655-3cde-489f-aa93-7869bcc0a802`, {
  method: "DELETE",
});
```

### Response:

```js
{
  "success": true,
  "message": {
    "id": "b52c4655-3cde-489f-aa93-7869bcc0a802",
    "createdAt": "2023-07-09T16:40:33.447Z",
    "text": "hi2",
    "parentId": "caa490bf-d915-4419-86d0-e6fe95c74239",
    "likes": 10
  }
}
```
