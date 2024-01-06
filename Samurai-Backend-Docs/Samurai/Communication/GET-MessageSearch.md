---
tags:
  - Done
---
# Пошук повідомлень

Method: `GET`
Endpoint: `/api/communication/message/search`
Description: Дозволяє гнучко знайти повідомлення. З пагінацією, на випадок великої вибірки повідомлень.

## Параметри:
- time_from: `datetime` - ISO 8601
- time_unitll: `datetime` - ISO 8601
- message_type: `MessageTypeEnum (string): [text, file]` - Фільтрація за типом повідомлення
- message_content: MessageContent - Фільтрація за змістом
- page: int = 1 - Від 1 до нескінченності.
- page_size: int = 25 - Скільки елементів "розмістити" у одній сторінці.

MessageContent (object):
Має бути присутнім лише один з двох параметрів (чи text, чи file)
У `file` можна будь-який з двох параметрів, чи обидва.
```json
{
	"text": "Part of the message",
	"file": {
		"extension": [
			"jpg",
			"png",
			"..."
		],
		"filename": "Part or full filename, inclding extensions"
	}
}
```

## Детальний опис

*Примітка:*
Якщо буде передано `message_type` = `text`, а у `message_content` - `file`, то бекенд буде вважати такий запит недійсним. Так само і навпаки.

### 400 - Invalid Request
Було вказано несумісні параметри.
Як приклад - `time_unitll` < `time_from`, несумісність `message_type` та `message_content`, невірне значення для `message_type`...
```json
{
	"status": "error",
	"detail": {
		"parameter_name": "Error Description"
	}
}
```

### 200 - Messages Found:

```json
{
	"page": 1,  // Передано у запиті
	"pages_count": 1,  // Номер останньої сторінки
	"content": [
		{  // MessageModel
			"from": {  // ShortUserModel
				"id": "UUID",
				"first_name": "Ivan",
				"last_name": "Ivanov",
				"middle_name": "Ivanovich"
			},
			"text": "string or null",
			"file": {  // or null FileModel
				"file_path": "link",
				"file_size": "12.34MB",
				"file_type": "docx",
				"file_name": "Some Name.docx"
			},
			"created_at": "ISO 8601",
			"is_read": false, // Was this message read by anoyone in the chat
		},
		...
	]
]
}
```