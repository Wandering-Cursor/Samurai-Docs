---
tags:
  - Done
Updated At: 2023-12-28T14:26:00
---
## Встановити фото профіля

Method: `POST`
Endpoint: `/api/account/settings/profile-picture`
Description: Встановлює зображення на профіль

Параметри:
- `image`: bytes - зображення, поток байтів (Base64 encoded)
  for Artem: (learn how to do base64 encoding)


Потребує авторизації, доступний всім користувачам.
### Відповіді
### 200 - Встановлено

### 400 - Зображення/Запит не є валідним
