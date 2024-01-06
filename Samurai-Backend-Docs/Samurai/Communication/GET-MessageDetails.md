---
tags:
  - Done
---
# Деталі повідомлення

Method: `GET`
Endpoint: `/api/communication/message/get`
Description: Отримати повідомлення за його UUID

## Параметри:
- message_id: !UUID - ID Повідомлення, щоб отримати інформацію про нього

## Детальний опис:
Відображаються лише ті повідомлення, які користувач може побачити (тобто серед доступних йому чатів).

Можна використовувати для того, щоб робити посилання на повідомлення всередині чату.

### 200 - Повідомлення знайдено
```json
{  // ExtendedMessageModel, MessageModel
	"chat_id": "UUID", // From which chat the message came
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
}
```

### 404 - Повідомлення не знайдено
Було вказано невірний UUID/Чат не є доступним для цього користувача.