# Тест-кейсы: Модуль авторизации (Login)

**Тестируемая страница:** https://www.saucedemo.com/
**Окружение:** Google Chrome, Windows 10/11.

| ID | Название | Предусловия | Шаги | Ожидаемый результат | Статус |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **TC-LOG-01** | Успешный вход (standard_user) | Открыта главная страница | 1. Ввести `standard_user` в поле Username.<br>2. Ввести `secret_sauce` в поле Password.<br>3. Нажать кнопку Login. | Пользователь перенаправлен на страницу `/inventory.html`. Отображается список товаров. | Pass |
| **TC-LOG-02** | Вход с неверным паролем | Открыта главная страница | 1. Ввести `standard_user` в поле Username.<br>2. Ввести `wrong_password` в поле Password.<br>3. Нажать кнопку Login. | Появляется сообщение об ошибке: *"Epic sadface: Username and password do not match any user in this service"*. Вход не выполнен. | Pass |
| **TC-LOG-03** | Вход с пустым полем Username | Открыта главная страница | 1. Оставить поле Username пустым.<br>2. Ввести `secret_sauce` в поле Password.<br>3. Нажать кнопку Login. | Появляется сообщение об ошибке: *"Epic sadface: Username is required"*. | Pass |
| **TC-LOG-04** | Вход с пустым полем Password | Открыта главная страница | 1. Ввести `standard_user` в поле Username.<br>2. Оставить поле Password пустым.<br>3. Нажать кнопку Login. | Появляется сообщение об ошибке: *"Epic sadface: Password is required"*. | Pass |
| **TC-LOG-05** | Вход заблокированного пользователя | Открыта главная страница | 1. Ввести `locked_out_user` в поле Username.<br>2. Ввести `secret_sauce` в поле Password.<br>3. Нажать кнопку Login. | Появляется сообщение об ошибке: *"Epic sadface: Sorry, this user has been locked out."*. | Pass |
| **TC-LOG-06** | Вход problem_user и проверка UI | Открыта главная страница | 1. Ввести `problem_user` в поле Username.<br>2. Ввести `secret_sauce` в поле Password.<br>3. Нажать кнопку Login. | Пользователь попадает на страницу каталога. **Внимание:** нужно проверить, что изображения товаров отображаются некорректно (заложенный баг). | Fail (Баг) |

---
### Заметки тестировщика:
- Все проверки проводились в режиме инкогнито, чтобы исключить влияние кэша браузера.
- Пароль для всех пользователей: `secret_sauce`.
- Результаты по `problem_user` (TC-LOG-06) будут подробно описаны в баг-репорте `BUG-001.md`.
