---
tags:
  - Done
---
# Список чатів

Method: `GET`
Endpoint: `/api/communication/chat/list`
Description: Дозволяє отримати перелік чатів, в яких є користувач.

Параметри:
- name: string - Опціональний параметр для того щоб відфільтрувати чат за назвою

## Детальний опис

Завжди* повертає перелік чатів.
- * Якщо передано авторизацію, і вона валідна
### 200 - Результати
```json
[
	{ // ChatModel
		"id": "UUID",
		"name": "string",
		"participants": 5,
		"last_message": {  // MessageModel
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
	},
	...
]
```