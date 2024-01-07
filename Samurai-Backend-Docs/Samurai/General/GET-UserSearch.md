---
tags:
  - Done
---
# Пошук користувача

Method: `GET`
Endpoint: `/api/account/search`
Description: Пошук користувача за збігом email адреси

## Параметри:
- email: !string - Адреса, за якою ми хочемо знайти іншого користувача

## Детальний опис

Повертає інформацію про користувача за його email-адресою

### 200 - Found
```json
{  //ShortBaseUserModel
	"id": "3fa85f64-5717-4562-b3fc-2c963f66afa6",
	"account_type": "Base user/Student/Teacher/Overseer",
	"email": "input@example.com",
	"first_name": "John",
	"last_name": "Smith",
	"middle_name": "Johnathan",
}
```
### 404 - Not Found
