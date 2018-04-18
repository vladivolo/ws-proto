# WebSocket API - Specification
----
## Типы пересылаемых данных

|      Данные     |   Описание  |
|:---------------:|-------------|
| `user message` | Генерируемые пользователями сообщения |
| `user status` | Пользовательские статусы |

## user message


Формат сообщений в чатах, передаваемый с сервера
```json
{
  "time": 24545455252,
  "utid": "fe89fy4rbft7gbcctehdn38yxwhpl",
  "payload": "payload data",
  "payload_type_id": 101
  }
```


