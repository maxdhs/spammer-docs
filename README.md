# Spammer API Documentation

`export const API = "https://hmh-spammer.netlify.app"`

## GET /api/posts

### Request:

```js
fetch(`${API}/api/posts`);
```

### Response:

```js
{
  "success": true,
  "posts": [
    {
      "id": "cb30e5bf-b5f6-4e15-899b-4ee37227bde0",
      "text": "hi2",
      "likes": 0,
      "createdAt": "2023-12-04T20:17:24.629Z"
    },
    {
      "id": "094aaf9e-ec12-4097-86a7-9966c6e85c74",
      "text": "Step 3: profit",
      "likes": 3,
      "createdAt": "2023-12-04T20:16:48.073Z"
    },
    {
      "id": "af1748d5-b94f-45e1-bb53-34972df54eed",
      "text": "Step 2: ?",
      "likes": 1,
      "createdAt": "2023-12-04T20:16:41.225Z"
    },
    {
      "id": "2b0741a7-cbae-4085-9a6d-a22327fea160",
      "text": "Step 1: Collect all the underpants",
      "likes": 0,
      "createdAt": "2023-12-04T20:16:36.893Z"
    }
  ]
}

```

## POST /api/posts

### Request:

```js
fetch(`${API}/api/posts`, {
  method: "POST",
  headers: {
    "Content-Type": "application/json",
  },
  body: JSON.stringify({
    text: "hello back!",
  }),
});
```

### Response:

```js
{
  "success": true,
  "post": {
    "id": "d9b420f6-57f4-4112-a89e-26a98681c5b5",
    "text": "hello back!",
    "likes": 0,
    "createdAt": "2023-12-04T20:19:52.024Z"
  }
}
```

## PUT /api/posts/:postId

### Request:

```js
fetch(`${API}/api/posts/d9b420f6-57f4-4112-a89e-26a98681c5b5`, {
  method: "PUT",
  headers: {
    "Content-Type": "application/json",
  },
  body: JSON.stringify({
    text: "Bye!",
  }),
});
```

### Response:

```js
{
  "success": true,
  "post": {
    "id": "d9b420f6-57f4-4112-a89e-26a98681c5b5",
    "text": "hello back!",
    "likes": 0,
    "createdAt": "2023-12-04T20:19:52.024Z"
  }
}
```

## DELETE /api/posts/:postId

### Request:

```js
fetch(`${API}/api/posts/d9b420f6-57f4-4112-a89e-26a98681c5b5`, {
  method: "DELETE",
});
```

### Response:

```js
{
  "success": true,
  "post": {
    "id": "d9b420f6-57f4-4112-a89e-26a98681c5b5",
    "text": "hello back!",
    "likes": 0,
    "createdAt": "2023-12-04T20:19:52.024Z"
  }
}
```

## GET /api/posts/:postId/comments

### Request:

```js
fetch(`${API}/api/posts/af1748d5-b94f-45e1-bb53-34972df54eed/comments`);
```

### Response:

```js
{
  "success": true,
  "comments": [
    {
      "id": "24e2b4f1-dd48-4aa7-9583-4df9b6036cd3",
      "text": "What is step 2 though?",
      "createdAt": "2023-12-04T20:17:01.865Z",
      "postId": "af1748d5-b94f-45e1-bb53-34972df54eed"
    }
  ]
}
```

## POST /api/posts/:postId/comments

### Request:

```js
fetch(`${API}/api/posts/af1748d5-b94f-45e1-bb53-34972df54eed/comments`, {
  method: "PUT",
  headers: {
    "Content-Type": "application/json",
  },
  body: JSON.stringify({
    text: "im starting to think there is no step 2 ...",
  }),
});
```

### Response:

```js
{
  "success": true,
  "comment": {
    "id": "3ea77084-528d-4ca2-a52b-5d312dcb4208",
    "text": "im starting to think there is no step 2 ...",
    "createdAt": "2023-12-04T20:27:56.168Z",
    "postId": "af1748d5-b94f-45e1-bb53-34972df54eed"
  }
}
```

## POST /api/posts/:postId/likes

### Request:

```js
fetch(`${API}/api/posts/af1748d5-b94f-45e1-bb53-34972df54eed/likes`, {
  method: "POST",
});
```

### Response:

```js
{
  "success": true,
  "post": {
    "id": "af1748d5-b94f-45e1-bb53-34972df54eed",
    "text": "Step 2: ?",
    "likes": 2,
    "createdAt": "2023-12-04T20:16:41.225Z"
  }
}
```
