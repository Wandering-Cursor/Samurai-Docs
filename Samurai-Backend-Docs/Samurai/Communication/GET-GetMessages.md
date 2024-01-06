---
tags:
  - Done
---
# Отримати повідомлення

Method: `GET`
Endpoint: `/api/communication/chat/messages`
Description: Дозволяє отримати повідомлення в чаті, коли його відкрито

Параметри:
- chat_id: !UUID - ID чату, повідомлення якого треба побачити
- page_size: int = 50 - Завантажує інформацію про останні N повідомлень, за замовчуванням - 50 останніх повідомлень.

## Детальний опис
Використовується лише для отримання останніх повідомлень. Подальше завантаження історії треба виконувати через [[GET-WSS Subscribe To Chats|WebSocker підключення]]

### 200 - Чат знайдено, повідомлення
```json
[
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
```

### 404 - Чат не знайдено
Через те, що користувач не є учасником, чи чат було видалено, як приклад.