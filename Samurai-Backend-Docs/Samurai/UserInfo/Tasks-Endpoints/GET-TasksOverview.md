## Загальна інформація

Method: `GET`
Endpoint: `/api/student/tasks/overview`
Description: Статистика по задачам обраного проєкту (к-ть задач по статусам), останні задачі (якщо треба, Артем, підкажи своє бачення)

Параметри:
- `project_id` - необов'язковий, візьметься останній проєкт, якщо не передано. UUID проєкту з [[GET-LastProject]]

Віпдовіді:
### 200 - Проєкт знайдено
```json
{
	"statistics": {
		"total": 42,
		"by_status": {
			"new": 10,
			"in_progress": 2,
			"in_review": 3,
			"reopened": 2,
			"done": 25
		}
	},
	"recent": [
		{
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
				"last_sent_at": "2023-12-27T17:28:30Z"
			}
		}
	] // 5 нещодавніх задач
}
```

### 404 - Проєкт не знайдено
...