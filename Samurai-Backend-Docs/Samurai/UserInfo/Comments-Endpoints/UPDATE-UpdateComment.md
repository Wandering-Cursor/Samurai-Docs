---
Updated At: 2023-12-28T10:00:00
tags:
  - Done
---
## Отримати коментарі

Method: `UPDATE`
Endpoint: `/api/student/comments/update`
Description: Дозволяє оновити коментар, який було створено до цього

Параметри:
- `comment_id`: !UUID - ID коментаря, який користувач хоче оновити
- `file`: bytes - Зміст файлу у вигляді потоку байтів. Не обов'язковий
- `text`: string - Текст коментаря. Не обо'язковий

### Важливо знати
Коментар може містити текст або файл.
Тобто можна надіслати параметр `file` ЧИ параметр `text` обидва - визвуть помилку.

### Відповіді
### 200 - Коментар оновлено
```json
{
	"id": "UUID",
	"file": {
		"file_path": "link",
		"file_size": "12.34MB",
		"file_type": "docx"
	}, // Or with text instead
	"created_at": "ISO 8601/Timestamp",
	"updated_at": "ISO 8601/Timestamp" // If same as created - not updated
}
```

### 400 - Невірний запит (Файл не є файлом)
```json
{
	"error_code": "INVALID_FILE"
}
```

### 400 - Невірний запит
Якщо надіслати `file` ТА `text`, як приклад
```json
{
	"error_code": "INVALID_ARGUMENTS"
}
```

### 404 - Не знайдено коментар