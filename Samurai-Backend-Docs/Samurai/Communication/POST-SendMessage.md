---
tags:
  - Done
---
# Надіслати повідомлення

Method: `POST`
Endpoint: `/api/communication/message/send`
Description: Дозволяє надіслати повідомлення до чату

## Параметри:
- chat_id: !UUID - До якого чату надсилається повідомлення
- text: string - Текст повідомлення.
- file: bytes - Зміст файлу у вигляді потоку байтів.

## Детальний опис

### 201 - Повідомлення надіслано
```json
{  // MessageModel
	"from": {
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
}
```

### 404 - Чат не знайдено
Не вийшло надіслати повідомлення