# maxsite-to-jekyll
Конвертер записей из базы дынных MaxSite CMS в формат записей Jekyll

Cкрипт генерирует файлы с расширением .markdown для дальнешей публикации на статическом сайте, созданном с помощью Jekyll.

Файлы генерируются в папке `/posts` c названием `YYYY-MM-DD-title-of-the-post.markdown`

Скрипт обращается к основной таблице `mso_page` и создает фалы с YAML front matter на основе значений, содеравшихся в `page_id`, добавляя к ним также название поста, дату публикации, теги, категории, description, keywords (из таблиц `mso_meta` и `mso_category`).

##Использование##

- Скопировать содержание репозитария на сервер
- Задать параметры соединения с базой данных (хост, база данных, имя пользователя, пароль) в `application/config.php`
- Открыть скрипт `index.php` в браузере ==> если все удачно сработано, скрипт сгенерирует файлы и выведет их список.

Тестирован на локальном вэбсервере WAMP c базой данной, созданной на MaxSite версии 0.621. 

### Что пока не работает ###

- Форматирование самого текста записи в формат Markdown или HTML, eсли при написании постов использовался BB-Code и другие подобные плюшки с [квадратными скобкам]. Пока скрпит просто тянет неотфоматированные значения из `page_content`, поэтому если использовалось что-то вроде [url]...[/url] - оно так и будет присутствовать в тексте.

### TODO ###

- [ ] форматирование текста
- [ ] главная страница с кнопкой и логом
- [ ] генерация страниц для категорий
