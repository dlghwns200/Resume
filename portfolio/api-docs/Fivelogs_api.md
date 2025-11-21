# Fivelogs – API Documentation (Backend)

## Overview
Fivelogs is a blog that helps beginners of coding stay motivated and not give up.
This document describes the main REST API endpoints I implemented as the backend developer.

## Authentication

- JWT-based authentication
- Header: `Authorization: Bearer <token>`

## Endpoints

### Comment
<details>
<summary>1. Upload comment</summary> 
<div markdown="1">

**POST** '/api/comments/boards/{boardId}'

Request:

```json
{
  "boardId": 1,
  "comment": "content"
}
```

Response (201):

```json
{
  "id": 1,
  "boardId": 1,
  "comment": "edit content",
  "nickname": "Nickname",
  "likeCount": 0,
  "dislikeCount": 0,
  "deleted": false,
  "createdDate": "2025-04-14T10:30:00",
  "updatedDate": "2025-04-14T10:45:00",
  "replies": [],
  "likedByMe": false
}
```
</div>
</details>

<details>
<summary> 2. Read comment </summary>
<div markdown="1">

**PUT** "/api/comments/boards/{boardId}"

Request
```json
{
  "boardId": 1
}
```

Response:
```json
{ 
"id": 1,
"boardId": 1,  
"comment": "edit content",
"nickname": "Nickname",
"likeCount": 0,
"dislikeCount": 0,
"deleted": false,
"createdDate": "2025-04-14T10:30:00",
"updatedDate": "2025-04-14T10:45:00",
"replies": [],
"likedByMe": false
}
```

</div>
</details>

<details>
<summary>3. Edit comment</summary>
<div markdown="1">

**PUT** "/api/images/{imageId}"

```json
{
  "boardId": 1,
  "commentId": 1
}
```

Response:
```json
{
  "id": 1,
  "boardId": 1,
  "comment": "edit content",
  "nickname": "Nickname",
  "likeCount": 0,
  "dislikeCount": 0,
  "deleted": false,
  "createdDate": "2025-04-14T10:30:00",
  "updatedDate": "2025-04-14T10:45:00",
  "replies": [],
  "likedByMe": false
}
```


</div>
</details>

<details>
<summary>4. Delete comment</summary>
<div markdown="1">

**DELETE** "/api/comments/boards/{boardId}/{id}"

Request

```json
{
  "id": 1,
  "boardId": "1"
}
```

Response

```json
  204 No Content
```

</div>
</details>

<details>
<summary>5. Like comment</summary>
<div markdown="1">
**POST** "/api/comments/boards/{boardId}/{id}/reaction"

Request

```json
{
  "id": 1,
  "boardId": 1
}
```

Response

```json
{
  "id": 1,
  "boardId": 1,
  "comment": "edit content",
  "nickname": "Nickname",
  "likeCount": 1,
  "dislikeCount": 0,
  "deleted": false,
  "createdDate": "2025-04-14T10:30:00",
  "updatedDate": "2025-04-14T10:45:00",
  "replies": [],
  "likedByMe": false
}
```
</div>
</details>