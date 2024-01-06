---
tags:
  - Done
---
# Додати користувача в чат

Method: `POST`
Endpoint: `/api/communication/chat/add_member`
Description: Дозволяє додати користувача в чат

## Параметри:
- chat_id: !UUID - ID чату, в який треба додати нового користувача
- user_id: !UUID - ID нового учаснику (див. [[../General/GET-UserSearch|GET-UserSearch]])

## Детальний опис

### 200 - Користувача додано

### 404 - Не знайдено
```json
{
	"status": "error",
	"description": { // Лише одне з двох
		"chat_id": "Chat not found",
		"user_id": "User not found"
	}
}
```