---
Updated At: 2023-12-28T10:00:00
tags:
  - Done
---

## Отримати деталі по задачі

Method: `GET`
Endpoint: `/api/students/tasks/task`
Description: Отримати деталі по конкретній задачі


Параметри:
- `task_id`: !UUID - обов'язковий параметр, вказує те, для якої задачі ми будемо отримувати дані

Відповіді

### 200 - Задачу знайдено
```json
{
	"id": "UUID",
	"order": 1,
	"name": "Назва задачі",
	"description": "Опис задачі, пояснює, що саме треба зробити.",
	"state": "new",
	"reviewer": {
		"id": "UUID",
		"first_name": "Іван",
		"last_name": "Іванов"
	}, // Or null
	"due_date": "2023-12-27T17:28:50Z", //ISO 8601/UTC Unix Timestamp
	"comments": {
		"count": 123,
		"last_sent_at": "2023-12-27T17:28:30Z",
	},
	"updated_at": "ISO 8601/Timestamp"
}
```

### 400 - Задачу не знайдено
Чи тому вказано невірний UUID, чи її видалено, чи вона належить іншому користувачеві