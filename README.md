# Шаблон для написания телеграмм ботов

Для использования данного шаблона необходимо нажать на его странице кнопку "Use this template"

## Структура:
- .env.example - пример содержимого файла .env, в котором хранятся значения переменных окружения
- .gitignore - файл для системы контроля версий, в котором прописаны файлы и директории проекта, которые не нужно отслеживать
- main.py - точка входа в проект
- requirements.txt - файл с зависимостями
- config_data - пакет для хранения файлов с конфигурационными данными
- errors - пакет с модулями для обработки исключений, возникающих в процессе работы бота
- external_services - пакет с модулями для работы с API внешних сервисов
- filters - пакет с кастомными фильтрами для хэндлеров:
  + is_admin.py - модуль с функцией-фильтром, проверяющей пользователя, является ли он администратором бота
- handlers - пакет, в котором хранятся обработчики апдейтов:
  + admin.py - модуль с хэндлерами, срабатывающими на действия пользователя, если он является администратором бота
  + private_user.py - модуль с хэндлерами, срабатывающими на действия приватных пользователей
  + user.py - модуль с хэндлерами для пользователей с обычным статусом
- keyboards - пакет с модулями, в которых хранятся и/или динамически формируются клавиатуры, отправляемые пользователям ботом, в процессе взаимодействия:
  + keyboard_utils.py - вспомогательные функции/методы, помогающие формировать клавиатуры
  + set_menu.py - модуль для установки команд в нативную кнопку "Menu" вашего бота
- lexicon - пакет для хранения текстов - ответов бота на разных языках
- middlewares - пакет, в котором хранятся программы, которые работают с апдейтами до того момента, как они попадут в хэндлер:
  + throttling.py - модуль с функциями/методами, которые отсекают от хэндлеров апдейты, распознанные как флуд
  + i18n.py - модуль с миддлварью, определяющей локаль пользователя и подготавливающей соответствующие переводы для нужной локали. Имеет смысл, если делаем мультиязычного бота
- database - пакет с модулями для взаимодействия с базой данных:
  + methods.py - модуль с методами для работы с БД
  + models.py - модуль с ORM-моделями базы данных
- services -  модуль с реализацией бизнес-логики
- states - пакет с модулями, в которых описаны классы, отражающие возможные состояния пользователей, в процессе взаимодействия с ботом, для реализации машины состояний
- tests - пакет с тестами для тестирования работы бота
- utils - пакет для хранения вспомогательных модулей, которые нужны в процессе работы бота, но по смыслу не попали ни в одну из предыдущих категорий.
