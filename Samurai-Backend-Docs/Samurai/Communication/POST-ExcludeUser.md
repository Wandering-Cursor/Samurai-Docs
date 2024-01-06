---
tags:
  - Done
  - TBD
---
# Видалити користувача з чату

Method: `DELETE`
Endpoint: `/api/communication/chat/remove_member`
Description: Дозволяє видалити користувача з чату


Можливо цей ендпоінт має дозволяти видалити лише себе з чату?

## Параметри:
- chat_id: !UUID - ID чату, з якого треба видалити користувача
- user_id: !UUID - ID учасника, якого треба видалити (див. [[../General/GET-UserSearch|GET-UserSearch]])

## Детальний опис

### 200 - Користувача видалено

### 404 - Не знайдено
```json
{
	"status": "error",
	"description": { // Лише одне з двох
		"chat_id": "Chat not found",
		"user_id": "User not found" // Чи користувача немає в чаті, чи вказано невалідний UUID
	}
}
```