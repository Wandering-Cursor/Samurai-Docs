---
Updated At: 2023-12-28T10:00:00
tags:
  - Done
---
## Отримати перелік задач

Method: `GET`
Endpoint: `/api/students/tasks/list`
Description: Перелік задач по проєкту, з пагінацією.

Параметри:
- `project_id`: UUID - необов'язковий, візьметься останній проєкт, якщо не передано. UUID проєкту з [[GET-LastProject]]
- `page`: int (Default: 0) - Порядковий номер сторінки.
- `page_size`: int (Default: 25) - К-ть елементів на сторінку.

Відповіді
### 200 - Проєкт знайдено
```json
{
	"page": 0,
	"next_page_exists": true,
	"previous_page_exisits": false,
	"data": [
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
			"due_date": "2023-12-27T17:28:50Z",
			"comments": {
				"count": 123,
				"last_sent_at": "2023-12-27T17:28:30Z"
			},
			"updated_at": "ISO 8601"
		}
	]
}
```

return date/time in UTC, ISO 8601