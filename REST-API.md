## Rest Api
### Получение списка чатов пользователя с полной информацией по ним
```
GET /chat_list_info?user_id=1&token=wqerfdx32412
```
Совмещает следующие два вызова
TODO:
### Получение списка чатов пользователя
```
GET /chat_list?user_id=1&token=wqerfdx32412
```
#### Аттрибуты
* **user_id** - Уникальный идентификатор пользователя
* **token** - Токен
#### Ответ:
Массив объектов описывающих чат
```json
[
 {
  "id": 12345,
  "type_id": 1,
  "name": "Название чата",
  "admin_id": "3245123"
  "logo_url": "http://cdn.fanlive2018.ru/mr90fu04h.png",
  "avatar_url": "http://cdn.fanlive2018.ru/mr90fu04h.png",
  "post_id": 456,
  "user_count": 123,
  "mute": true,
 },
 {
  "id": 125,
  "type_id": 3,
  "name": "Название чата2",
  "admin_id": "3245123"
  "logo_url": "http://cdn.fanlive2018.ru/mr90fu04h.png",
  "avatar_url": "http://cdn.fanlive2018.ru/mr90fu04h.png",
  "post_id": 456,
  "user_count": 1239,
  "mute": false,
 },
]
```
#### Аттрибуты
* **id** - Уникальный идентификатор чата
* **type_id** - Тип чата. 1-P2P, 2-Груповой, 3-Командный, 4-Волонтерский
* **name** - Название чата
* **admin_id** ID администратора чата, если чат груповой
* **logo_url** - Лого группы (если группа)
* **avatar_url** Аватар чата / пользователя
* **post_id** ID Карточки, к которой привязан груповой чат или null
* **user_count** Количество пользователей в чате
* **is_mute** Статус оповещений (true - выключены, false - включены)

### Получение списка последних сообщений в чатах пользователя
```
GET /last_chat_msg?user_id=1&token=adfvalqjwemwc 
```
#### Аттрибуты
* **user_id** - Уникальный идентификатор пользователя
* **token** - Токен
#### Ответ:
```json
[
  {"chat_id": 32134123, "bin": "{...Что-то являющееся понятным для клиента...}"},
  {"chat_id": 32134123, "bin": "{...Что-то являющееся понятным для клиента...}"},
  {"chat_id": 32134123, "bin": "{...Что-то являющееся понятным для клиента...}"},
]

```
#### Аттрибуты
* **chat_id** - Уникальный идентификатор чата
* **bin** - Контейнер хранящий сообщение

### Получение списка сообщений в чате
```
GET /chat_msg?chat_id=1234&offset=3467345&limit=100&order=ASC&user_id=1&token=afdsgrthncjfg
```
#### Аттрибуты
* **chat_id** - Уникальный идентификатор чата
* **offset** - Иденитификатор отправного сообщения
* **limit** - Кол-во сообщений в выборке
* **order** - Направление выборки ("ASC" - по возрастанию id сообщений, "DESC" - по убыванию)
* **user_id** - Уникальный идентификатор пользователя
* **token** - Токен
#### Ответ:
```json
[
 {"id": 234523, "bin": "..."},
 {"id": 234523, "bin": "..."},
 {"id": 234523, "bin": "..."},
 ...
]
```
