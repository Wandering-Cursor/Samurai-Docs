---
Updated At: 2023-12-28T10:00:00
tags:
  - Done
---
## Зміна статусу

Method: `UPDATE`
Endpoint: `/api/students/tasks/move_task`
Description: Дозволяє вказати новий статус для задачі

Параметри (JSON в тілі запиту):
- `task_id`: !UUID - По якій задачі змінюється статус
- `state`: string (TaskStatusesEnum) - який статус має придбати задача

Відповіді

### 200 - Статус змінено

### 403 - Зміна статусу заборонена

### 404 - Задачу не знайдено
