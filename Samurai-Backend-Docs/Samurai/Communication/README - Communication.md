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

## [POST-CreateChat](POST-CreateChat.md)
## [GET-ChatsList](GET-ChatsList.md)
## [POST-AddUser](POST-AddUser.md) (to Chat)

## [POST-LeaveChat](POST-LeaveChat.md)

## [GET-GetMessages](GET-GetMessages.md)
## [POST-SendMessage](POST-SendMessage.md)

## [PUT-UpdateMessage](PUT-UpdateMessage.md) #TBD 

## [DELETE-DeleteMessage](DELETE-DeleteMessage.md) #TBD 

## [GET-MessageSearch](GET-MessageSearch.md)

## [GET-MessageDetails](GET-MessageDetails.md)

## [GET-WSS Subscribe To Chats](GET-WSS_SubscribeToChats.md)
