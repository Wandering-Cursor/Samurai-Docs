---
tags:
  - Done
  - TBD
---
# Видалити користувача з чату

Method: `DELETE`
Endpoint: `/api/communication/chat/leave`
Description: Дозволяє покинути чат

## Параметри:
- chat_id: !UUID - ID чату, з якого треба вийти

## Детальний опис

### 200 - Користувач покинув чат

### 404 - Не знайдено
```json
{
	"status": "error",
	"description": {
		"chat_id": "Chat not found",
	}
}
```