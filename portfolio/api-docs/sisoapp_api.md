# SisoApp – API Documentation (Backend)

## Overview
SisoApp is a senior-care matching application.  
This document describes the main REST API endpoints I implemented as the backend developer.

## Authentication

- JWT-based authentication
- Header: `Authorization: Bearer <token>`

## Endpoints

### Images
<details>
<summary>1. Upload Image</summary> 
<div markdown="1">

**POST** '/api/images/upload'

Request:

```json
{
  "file": MBTI.jpg, image.png
}
```

Response (201):

```json
 {
    "id": 1,
    "userId": 3,
    "path": "https://siso-siso-dlghwns-siso.s3.ap-northeast-2.amazonaws.com/images/3/3554c7de-38a2-4f91-8a54-deb6f3aa3040-MBTI.png",
    "serverImageName": "3554c7de-38a2-4f91-8a54-deb6f3aa3040-MBTI.png",
    "originalName": "MBTI.png",
    "presignedUrl": "https://siso-siso-dlghwns-siso.s3.ap-northeast-2.amazonaws.com/images/3/3554c7de-38a2-4f91-8a54-deb6f3aa3040-MBTI.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Date=20250903T142027Z&X-Amz-SignedHeaders=host&X-Amz-Credential=AKIA6OFPVS75ALC66M5C%2F20250903%2Fap-northeast-2%2Fs3%2Faws4_request&X-Amz-Expires=900&X-Amz-Signature=33153f7d6f1c0fa59c40745f9e312033705b188c600f037601f3df6a07982913",
    "presignedUrlExpiresAt": "2025-09-03T23:25:27.0270891",
    "presignedUrlType": "DEFAULT",
    "presignedUrlValid": true,
    "createdAt": "2025-09-03T23:20:26.8965303",
    "updatedAt": "2025-09-03T23:20:26.8965303"
  },
  {
    "id": 2,
    "userId": 3,
    "path": "https://siso-siso-dlghwns-siso.s3.ap-northeast-2.amazonaws.com/images/3/e30dc76a-273f-4b20-9b8a-23a5230c38c1-image.png",
    "serverImageName": "e30dc76a-273f-4b20-9b8a-23a5230c38c1-image.png",
    "originalName": "image.png",
    "presignedUrl": "https://siso-siso-dlghwns-siso.s3.ap-northeast-2.amazonaws.com/images/3/e30dc76a-273f-4b20-9b8a-23a5230c38c1-image.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Date=20250903T142027Z&X-Amz-SignedHeaders=host&X-Amz-Credential=AKIA6OFPVS75ALC66M5C%2F20250903%2Fap-northeast-2%2Fs3%2Faws4_request&X-Amz-Expires=900&X-Amz-Signature=f9e374295b228a825d4934df911b227f968cb1564700d0b22ac3ddbfe324ed06",
    "presignedUrlExpiresAt": "2025-09-03T23:25:27.1279007",
    "presignedUrlType": "DEFAULT",
    "presignedUrlValid": true,
    "createdAt": "2025-09-03T23:20:27.0954077",
    "updatedAt": "2025-09-03T23:20:27.0954077"
  }
```
</div>
</details>

<details>
<summary> 2. Read Images </summary>
<div markdown="1">

**GET** "/api/images/me"

Response:
```json
{
    "id": 1,
    "userId": 3,
    "path": "https://siso-siso-dlghwns-siso.s3.ap-northeast-2.amazonaws.com/images/3/3554c7de-38a2-4f91-8a54-deb6f3aa3040-MBTI.png",
    "serverImageName": "3554c7de-38a2-4f91-8a54-deb6f3aa3040-MBTI.png",
    "originalName": "MBTI.png",
    "presignedUrl": "https://siso-siso-dlghwns-siso.s3.ap-northeast-2.amazonaws.com/images/3/3554c7de-38a2-4f91-8a54-deb6f3aa3040-MBTI.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Date=20250903T142027Z&X-Amz-SignedHeaders=host&X-Amz-Credential=AKIA6OFPVS75ALC66M5C%2F20250903%2Fap-northeast-2%2Fs3%2Faws4_request&X-Amz-Expires=900&X-Amz-Signature=33153f7d6f1c0fa59c40745f9e312033705b188c600f037601f3df6a07982913",
    "presignedUrlExpiresAt": "2025-09-03T23:25:27.0270891",
    "presignedUrlType": "DEFAULT",
    "presignedUrlValid": true,
    "createdAt": "2025-09-03T23:20:26.8965303",
    "updatedAt": "2025-09-03T23:20:26.8965303"
  },
  {
    "id": 2,
    "userId": 3,
    "path": "https://siso-siso-dlghwns-siso.s3.ap-northeast-2.amazonaws.com/images/3/e30dc76a-273f-4b20-9b8a-23a5230c38c1-image.png",
    "serverImageName": "e30dc76a-273f-4b20-9b8a-23a5230c38c1-image.png",
    "originalName": "image.png",
    "presignedUrl": "https://siso-siso-dlghwns-siso.s3.ap-northeast-2.amazonaws.com/images/3/e30dc76a-273f-4b20-9b8a-23a5230c38c1-image.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Date=20250903T142027Z&X-Amz-SignedHeaders=host&X-Amz-Credential=AKIA6OFPVS75ALC66M5C%2F20250903%2Fap-northeast-2%2Fs3%2Faws4_request&X-Amz-Expires=900&X-Amz-Signature=f9e374295b228a825d4934df911b227f968cb1564700d0b22ac3ddbfe324ed06",
    "presignedUrlExpiresAt": "2025-09-03T23:25:27.1279007",
    "presignedUrlType": "DEFAULT",
    "presignedUrlValid": true,
    "createdAt": "2025-09-03T23:20:27.0954077",
    "updatedAt": "2025-09-03T23:20:27.0954077"
  }
```

</div>
</details>

<details>
<summary>3. Edit images</summary>
<div markdown="1">

**PUT** "/api/images/{imageId}"

Request

```json
{
  "imageId": "1"
}
```

Response

```json
{
  "id": 1,
  "userId": 123,
  "path": "https://cdn.example.com/images/profile1_updated.jpg",
  "serverImageName": "e30dc76a-273f-4b20-9b8a-23a5230c38c1-image.png",
  "originalName": "image.png",
  "presignedUrl": "https://siso-siso-dlghwns-siso.s3.ap-northeast-2.amazonaws.com/images/3/e30dc76a-273f-4b20-9b8a-23a5230c38c1-image.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Date=20250903T142027Z&X-Amz-SignedHeaders=host&X-Amz-Credential=AKIA6OFPVS75ALC66M5C%23%2Fap-northeast-2%2Fs3%2Faws4_request&X-Amz-Expires=900&X-Amz-Signature=f9e374295b228a825d4934df911b227f968cb1564700d0b22ac3ddbfe324ed06",
  "presignedUrlExpiresAt": "2025-09-03T23:25:27.1279007",
  "presignedUrlType": "DEFAULT",
  "presignedUrlValid": true,
  "createdAt": "2025-09-03T23:24:27.0954077",
  "updatedAt": "2025-09-03T23:24:27.0954077"
}
```


</div>
</details>

<details>
<summary>4. Delete Images</summary>
<div markdown="1">

**DELETE** "/api/images/{imageId}"

Request

```json
{
  "imageId": "1"
}
```

Response

```json
  204 No Content
```

</div>
</details>

<details>
<summary>Error code</summary>
<div markdown="1">

```json
IMAGE_NOT_FOUND(HttpStatus.NOT_FOUND, "Cannot find images."),
IMAGE_EMPTY(HttpStatus.NOT_FOUND, "Images are empty"),
IMAGE_UPLOAD_PERSIST_FAIL(HttpStatus.INTERNAL_SERVER_ERROR,"Image is not available to save in storage"),
IMAGE_MAX_COUNT_EXCEEDED(HttpStatus.BAD_REQUEST, "You exceeds the maximum amounts of images"),
IMAGE_ACCESS_DENIED(HttpStatus.FORBIDDEN, "Cannot access to image"),
```
</div>
</details>

### Voices
<details>
<summary>1. Upload Voice</summary> 
<div markdown="1">

**POST** '/api/voice-samples/upload'

Request:

```json
{
  "file": test.m4a
}
```

Response (201):

```json
 {
  "id": 1,
  "userId": 1,
  "url": "https://siso-siso-dlghwns-siso.s3.ap-northeast-2.amazonaws.com/voices/1/64a9cebf-0263-4e9c-8b08-5dea9c376b89-__.m4a",
  "duration": 6,
  "fileSize": 159470,
  "presignedUrl": "https://siso-siso-dlghwns-siso.s3.ap-northeast-2.amazonaws.com/voices/1/64a9cebf-0263-4e9c-8b08-5dea9c376b89-__.m4a?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Date=20250903T145357Z&X-Amz-SignedHeaders=host&X-Amz-Credential=AKIA6OFPVS75ALC66M5C%2F20250903%2Fap-northeast-2%2Fs3%2Faws4_request&X-Amz-Expires=600&X-Amz-Signature=6f14cce5d060f25a7dd8d356b38560adc3a8b5ffb970aa6a23a5d720fb28f4b3",
  "presignedUrlExpiresAt": "2025-09-04T00:03:57.4690137",
  "presignedUrlValid": true,
  "createdAt": "2025-09-03T23:53:57.2046047",
  "updatedAt": "2025-09-03T23:53:57.2046047"
}
```
</div>
</details>

<details>
<summary> 2. Read voices </summary>
<div markdown="1">

**GET** "/api/voice-samples/me"

Response:
```json
{
  "id": 1,
  "userId": 1,
  "url": "https://siso-siso-dlghwns-siso.s3.ap-northeast-2.amazonaws.com/voices/1/64a9cebf-0263-4e9c-8b08-5dea9c376b89-__.m4a",
  "duration": 6,
  "fileSize": 159470,
  "presignedUrl": "https://siso-siso-dlghwns-siso.s3.ap-northeast-2.amazonaws.com/voices/1/64a9cebf-0263-4e9c-8b08-5dea9c376b89-__.m4a?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Date=20250903T145357Z&X-Amz-SignedHeaders=host&X-Amz-Credential=AKIA6OFPVS75ALC66M5C%2F20250903%2Fap-northeast-2%2Fs3%2Faws4_request&X-Amz-Expires=600&X-Amz-Signature=6f14cce5d060f25a7dd8d356b38560adc3a8b5ffb970aa6a23a5d720fb28f4b3",
  "presignedUrlExpiresAt": "2025-09-04T00:03:57.4690137",
  "presignedUrlValid": true,
  "createdAt": "2025-09-03T23:53:57.2046047",
  "updatedAt": "2025-09-03T23:53:57.2046047"
}
```

</div>
</details>

<details>
<summary>3. Edit voices</summary>
<div markdown="1">

**PUT** "/api/voice-samples/{voiceId}"

Request

```json
{
  "voiceId": "1"
}
```

Response

```json
{
  "id": 1,
  "userId": 1,
  "url": "https://siso-siso-dlghwns-siso.s3.ap-northeast-2.amazonaws.com/voices/1/64a9cebf-0263-4e9c-8b08-5dea9c376b89-__.m4a",
  "duration": 6,
  "fileSize": 159470,
  "presignedUrl": "https://siso-siso-dlghwns-siso.s3.ap-northeast-2.amazonaws.com/voices/1/64a9cebf-0263-4e9c-8b08-5dea9c376b89-__.m4a?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Date=20250903T145357Z&X-Amz-SignedHeaders=host&X-Amz-Credential=AKIA6OFPVS75ALC66M5C%2F20250903%2Fap-northeast-2%2Fs3%2Faws4_request&X-Amz-Expires=600&X-Amz-Signature=6f14cce5d060f25a7dd8d356b38560adc3a8b5ffb970aa6a23a5d720fb28f4b3",
  "presignedUrlExpiresAt": "2025-09-04T00:03:57.4690137",
  "presignedUrlValid": true,
  "createdAt": "2025-09-03T23:53:57.2046047",
  "updatedAt": "2025-09-03T23:53:57.2046047"
}
```


</div>
</details>

<details>
<summary>4. Delete Voice </summary>
<div markdown="1">

**DELETE** "/api/voice-samples/{voiceId}"

Request

```json
{
  "voiceId": "1"
}
```

Response

```json
  204 No Content
```

</div>
</details>

<details>
<summary>Error code</summary>
<div markdown="1">

```json
VOICE_SAMPLE_NOT_FOUND(HttpStatus.NOT_FOUND, "Cannot find voice-samples"),
VOICE_SAMPLE_FILE_EMPTY(HttpStatus.BAD_REQUEST, "There is no voice-samples file"),
VOICE_SAMPLE_INVALID_FILENAME(HttpStatus.BAD_REQUEST, "File-extensions of voice files are not valid"),
VOICE_SAMPLE_UNSUPPORTED_FORMAT(HttpStatus.BAD_REQUEST, "This files does not support"),
VOICE_SAMPLE_FILE_TOO_LARGE(HttpStatus.BAD_REQUEST, "Too large for voice files"),
VOICE_SAMPLE_MAX_COUNT_EXCEEDED(HttpStatus.BAD_REQUEST, "Too many files for voice files"),
VOICE_SAMPLE_UPLOAD_FAILED(HttpStatus.INTERNAL_SERVER_ERROR, "Failed to upload voice files"),
VOICE_SAMPLE_INVALID_PATH(HttpStatus.BAD_REQUEST, "Invalid path for voice files"),
VOICE_SAMPLE_FILE_TOO_LONG(HttpStatus.BAD_REQUEST, "Voice duration is too large");
```
</div>
</details>