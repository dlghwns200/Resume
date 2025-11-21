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

**POST** '/api/images/upload'

Request:

```json
{
  "Token": abcdefghijklmn,
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
</details>


