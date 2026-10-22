# Тестирование API (Manual)

В данном разделе представлены результаты ручного тестирования публичного API `dummyjson.com` с использованием Postman.

### Проверенные эндпоинты:
1. `GET /products/1` — получение информации о товаре по ID.
   - *Ожидаемый результат:* 200 OK, JSON-объект с полями `title`, `price`, `category`.
   - *Фактический результат:* 200 OK.
   <img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/e82754ae-6e2a-4bf5-ba40-050cabbe0e7e" />


2. `GET /products` — получение списка товаров.
   - *Ожидаемый результат:* 200 OK, JSON-объект с массивом `products`.
   - *Фактический результат:* 200 OK.
   <img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/1ff8d582-b434-4afd-90ac-79e4c8da7593" />


3. `POST /products/add` — создание нового товара (имитация).
   - *Ожидаемый результат:* 201 Created, в ответе есть новый `id`.
   - *Фактический результат:* 201 Created.
   <img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/888bbb39-5a60-4509-ace0-bb3b2cd3dc03" />


4. `GET /products/99999` — запрос несуществующего товара.
   - *Ожидаемый результат:* 404 Not Found.
   - *Фактический результат:* 404 Not Found.
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/90722a0e-e56c-41ff-943c-ee50ffbbc004" />
