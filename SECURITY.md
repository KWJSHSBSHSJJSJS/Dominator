# Политика безопасности

## Поддерживаемые версии

До выхода проекта в стабильную версию поддерживается только последняя версия и все предыдущие версии не страше недели.

Позже тут появится таблица поддерживаемых версий.

## Сообщение об уязвимости

Данное сообщение должно содержать в себе несколько пунктов.

- Версия бота. (Например, `0.0.0.1`).
- Версия Python и ОС (Например, `Python 3.8.3, Windows 10`).
- Версии используемых библиотек из `requirements.txt` **списком**. Например: 
    ```
    dicord.py 1.3.3
    somelibrary 1.0
    anotherlib 4.10.453
    ```
- Описание уязвимости. Например:

    При вызове функции `abc` с аргументом `42`, командой `$ABCfunc` в текстовом канале
Discord-сервера, происходит краш бота с сообщением об ошибке: `Error: Invalid argument '42' (str) of function abc()` и становится доступна внутренняя функция проверки ID пользователя, недоступная непривилегированным юзерам.

- Возможная причина уязвимости (если не знаете, напишите "Причина мне неизвестна" или что-то подобное, не пропускайте этот пункт).
Например:

    Скорее всего ошибка возникает из-за неверного типа данных `str` вместо `int`. А уязвимость - из-за отсутствия проверки на права пользователя.

- Ваше решение уязвимости (если не знаете, напишите об этом, не оставляйте пустое место). Например:

    Для устранения ошибки, наверное надо:
    ```python
    # Преобразовываем типы:
    
    # ... 
    newarg = int(arg)
    # ...
    
    # И используем проверку юзера на доступность ему права управления пользователями:
    
    # ...
    if User.permissions.canManageUsers:
        pass
    else:
        Chat.newMessage('Вы не имеете права управлять пользователями!')
    # ...
    ```
    
    И ко всему этому следует применять форматирование MarkDown. Это тоже очень важно.

*P.S. Весь код конечно же выдуман. Это не реальная уязвимость, да и код тоже выдуман.*