---
Updated At: 2023-12-28T10:00:00
tags:
  - Done
---
## Отримати коментарі

Method: `GET`
Endpoint: `/api/students/comments/list`
Description: Дозволяє отримати пагінований перелік коментарів задачі

Параметри:
- `task_id`: !UUID - ID [[GET-TaskDetails|Задачі]], по якій користувач хоче отримати коментарі
- `page`: int (Default: 0) - Порядковий номер сторінки.
- `page_size`: int (Default: 25) - К-ть елементів на сторінку.

### Важливо знати
Коментар може містити текст або файл.

### Відповіді
### 200 - Перелік коментарів для задачі
```json
{
	"page": 0,
	"next_page_exists": true,
	"previous_page_exisits": false,
	"data": [
		{
			"id": "UUID",
			"file": {
				"file_path": "link",
				"file_size": "12.34MB",
				"file_type": "docx"
			},
			"created_at": "ISO 8601/Timestamp",
			"updated_at": "ISO 8601/Timestamp" // If same as created - not updated
		},
		{
			"id": "UUID-2",
			"text": "Probably a long comment of some sort",
			"created_at": "ISO 8601/Timestamp",
			"updated_at": "ISO 8601/Timestamp" // If same as created - not updated
		}
	]
}
```

### 404 - Задачу не знайдено
