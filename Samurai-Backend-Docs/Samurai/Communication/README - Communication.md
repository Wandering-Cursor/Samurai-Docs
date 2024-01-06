---
tags:
  - Document
  - TODO
---
# Загальний опис
Тут описані ендпоінти необхідні для спілкування.

Наразі все спілкування полягає в створенні чату між одним/декількома користувачами, які можуть надсилати повідомлення один одному.
Повідомлення, як і коментарі складаються з тексту ЧИ файлу.

Для того щоб додати користувачів у чат - треба знати їх пошту ЧИ UUID. (Маючи перше - можна отримати останнє, див. [[../General/GET-UserSearch|GET-UserSearch]], [[../General/GET-FuzzyUserSearch|GET-FuzzyUserSearch]])

# Ендпоінти

## [POST-CreateChat](POST-CreateChat)
## [GET-ChatsList](GET-ChatsList)
## [POST-AddUser](POST-AddUser) (to Chat)

## [POST-ExcludeUser](POST-ExcludeUser) (from Chat)

## [GET-GetMessages](GET-GetMessages)
## [POST-SendMessage](POST-SendMessage)

## [PUT-UpdateMessage](PUT-UpdateMessage)

## [DELETE-DeleteMessage](DELETE-DeleteMessage)

## [GET-ChatSearch](GET-ChatSearch)

## [GET-MessageDetails](GET-MessageDetails)

## [GET-WSS Subscribe To Chats](GET-WSS_SubscribeToChats)
