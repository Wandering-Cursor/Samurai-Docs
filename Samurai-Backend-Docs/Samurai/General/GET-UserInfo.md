---
tags:
  - Done
---
# Інформація про користувача

Method: `GET`
Endpoint: `/api/accounts/account-info/`
Description: Short. Precise. To the point.

## Параметри:
- account_id: UUID — Необов'язковий параметр UUID користувача.

## Детальний опис
Якщо не передати account_id - поверне інформацію про поточного користувача.

Відповіді:
Можна побачити у https://api.obscurial.art/swagger/

### 200 - Ok
```json
{
  "base": {
    "id": "3fa85f64-5717-4562-b3fc-2c963f66afa6",
    "account_type": "Base user",
    "email": "user@example.com",
    "first_name": "string",
    "last_name": "string",
    "middle_name": "string",
    "profile_picture": "string"
  },
  "student": {
    "id": "3fa85f64-5717-4562-b3fc-2c963f66afa6",
    "account_type": "Student",
    "email": "user@example.com",
    "first_name": "string",
    "last_name": "string",
    "middle_name": "string",
    "profile_picture": "string",
    "group": {
      "id": 0,
      "name": "string",
      "faculty": {
        "id": 0,
        "name": "string"
      }
    }
  },
  "teacher": {
    "id": "3fa85f64-5717-4562-b3fc-2c963f66afa6",
    "account_type": "Teacher",
    "email": "user@example.com",
    "first_name": "string",
    "last_name": "string",
    "middle_name": "string",
    "profile_picture": "string",
    "faculties": [
      "string"
    ],
    "contact_information": "string"
  },
  "overseer": {
    "id": "3fa85f64-5717-4562-b3fc-2c963f66afa6",
    "account_type": "Overseer",
    "email": "user@example.com",
    "first_name": "string",
    "last_name": "string",
    "middle_name": "string",
    "profile_picture": "string",
    "faculty": 0
  }
}
```

### 401 - Unauthorized
```json
{
  "detail": "Authentication credentials were not provided."
}
```

### 404 - Not Found