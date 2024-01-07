---
tags:
  - Done
---
# Неточний пошук користувача

Method: `GET`
Endpoint: `/api/account/fuzzy-search`
Description: Пошук користувача за збігом email адреси, чи її частини

## Параметри:
- email: !string - Адреса/її частина, за якою ми хочемо знайти іншого користувача

## Детальний опис
Доступний лише Teacher, Overseer.

Як приклад:

| uuid | email |
| ---- | ---- |
| 12345-abcde-12345 | tester@mail.com |
| 12345-abcde-54321 | tester2@mail.com |
| 12345-abcde-abcdef | oleg@mail.com |

При пошуку на такому ендпоінті, якщо вказати у пошуку email = "test" - повернуться записи про:
- teset@mail.com
- tesetr2@mail.com

Головна різниця від [[GET-UserSearch]] полягає у тому, що цей ендпоінт дозволяє шукати людей за частковим вказанням ємейлу.

### 200 - Ok
```json
[
	{  //ShortBaseUserModel
		"id": "3fa85f64-5717-4562-b3fc-2c963f66afa6",
		"account_type": "Base user/Student/Teacher/Overseer",
		"email": "input@example.com",
		"first_name": "John",
		"last_name": "Smith",
		"middle_name": "Johnathan",
	},
	...
]
```