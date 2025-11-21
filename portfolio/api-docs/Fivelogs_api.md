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
  "likedByMe": null
}
```
</div>
</details>

<details>
<summary> 2. Read comment </summary>
<div markdown="1">

**GET** "/api/comments/boards/{boardId}"

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
"likedByMe": null
}
```

</div>
</details>

<details>
<summary>3. Edit comment</summary>
<div markdown="1">

**PUT** "/api/comments/boards/{booardId}/{imageId}"

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
  "likedByMe": null
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
  "likedByMe": true
}
```
</div>
</details>

<details>
<summary>5. Read replies comment</summary>
<div markdown="1">
**GET** "/api/comments/boards/{parentId}/replies"

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
  "comment": "content",
  "nickname": "Nickname",
  "likeCount": 0,
  "dislikeCount": 0,
  "deleted": false,
  "createdDate": "2025-04-14T10:30:00",
  "updatedDate": "2025-04-14T10:45:00",
  "replies": [
    {
      "id": 2,
      "comment": "reply content",
      "nickname": "ReplyUser",
      "likeCount": 0,
      "dislikeCount": 0,
      "deleted": false,
      "createdDate": "2025-04-14T10:40:00",
      "updatedDate": null,
      "replies": [],
      "likedByMe": null
    }
  ],
  "likedByMe": true

}
```
</div>
</details>


### Blogs

<details>
<summary>1. Edit Board</summary>
<div markdown="1">

**PUT** "/api/images/{imageId}"

```json
{
  "boardId": 1
}
```

Response:
```json
{
  "boardId": 1,
  "blogTitle": "Edit title",
  "nickname": "Nickname",
  "createdDate": "2025-04-14T10:30:00",
  "updatedDate": "2025-04-14T11:00:00",
  "status": "PUBLIC",
  "hashtags": ["Java", "Spring"]
}
```


</div>
</details>


<details>
<summary>2. Delete board</summary>
<div markdown="1">

**DELETE** "/api/comments/boards/{boardId}"

Request

```json
{
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
<summary>3. Search boards</summary>
<div markdown="1">

**GET** "/api/boards/search"


Response

```json
[
  {
    "id": 12,
    "title": "Spring Boot 게시판 만들기",
    "content": "내용 일부...",
    "views": 230,
    "hashtags": ["Spring", "JPA"],
    "created": "2025-04-14 10:30:00",
    "updated": "2025-04-14 11:00:00",
    "nickname": "Nickname",
    "githubLink": "https://github.com/example",
    "instagramLink": null,
    "twitterLink": null,
    "boardStatus": "PUBLIC"
  }
]
```


</div>
</details>


### Profile
<details><
<summary>SNS link</summary>
<div markdown="1">
</div>
</details>