## Rest Api
### Получение списка чатов пользователя
```
GET /chat_list?user_id=1&token=wqerfdx32412
```
#### Аттрибуты
* **user_id** - Уникальный идентификатор пользователя
* **token** - Токен
#### Ответ
```json
[
 {
  "id": 12345,
  "type_id": 1,
  "name": "Название чата",
  "logo_url": "http://cdn.fanlive2018.ru/mr90fu04h.png",
  "avatar_url": "http://cdn.fanlive2018.ru/mr90fu04h.png",
  "post_id": 456,
  "mute": true,
 },
 {
  "id": 125,
  "type_id": 3,
  "name": "Название чата2",
  "logo_url": "http://cdn.fanlive2018.ru/mr90fu04h.png",
  "avatar_url": "http://cdn.fanlive2018.ru/mr90fu04h.png",
  "post_id": 456,
  "mute": false,
 },
]
```
#### Аттрибуты
* **id** - Уникальный идентификатор чата
* **type_id** - Тип чата. 1-P2P, 2-Груповой, 3-Командный, 4-Волонтерский
* **name** - Название чата
* **logo_url** - Лого группы (если группа)
* **avatar_url** Аватар чата / пользователя
* **post_id** ID Карточки, к которой привязан груповой чат или null
* **is_mute** Статус оповещений (true - выключены, false - включены)

### Получение списка последних сообщений в чатах
```
GET /last_chat_msg?user_id=1&token=adfvalqjwemwc 
```
### Получение списка сообщений в чате
```
GET /chat_msg?chat_id=1234&offset=3467345&limit=100&order=ASC&user_id=1&token=afdsgrthncjfg
```
