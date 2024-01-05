# Загальний опис
Тут описані ендпоінти необхідні для спілкування.

Наразі все спілкування полягає в створенні чату між одним/декількома користувачами, які можуть надсилати повідомлення один одному.
Повідомлення, як і коментарі складаються з тексту ЧИ файлу.

Для того щоб додати користувачів у чат - треба знати їх пошту ЧИ UUID. (Маючи перше - можна отримати останнє, див. [[../General/GET-UserSearch|GET-UserSearch]], [[../General/GET-FuzzyUserSearch|GET-FuzzyUserSearch]])

# Ендпоінти

## [[POST-CreateChat]]
## [[GET-ChatsList]]
## [[POST-AddUser]] (to Chat)

## [[POST-ExcludeUser]] (from Chat)

## [[GET-GetMessages]]
## [[POST-SendMessage]]

## [[PUT-UpdateMessage]]

## [[DELETE-DeleteMessage]]

## [[GET-WSS Subscribe To Chats]]
