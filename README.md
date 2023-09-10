
# EDYK-RecSystem

Инструмент разработанный для вычисления рекомендаций видео для пользователей. В нем используется смешанный тип рекомендательной системы.

В нем используются направления контент-направленного типа:
используя атрибуты удержания просмотра и эмоции, мы создаем систему рейтингов, благодаря которой пользователю рекомендуется определенное видео из определенных категорий.

# Установка
Для начала требуется установить PostgreSQL 14 версии и выше. 
Создать там базу данных c любым названием.

После чего необходимо заполнить конфиги.
В репозитории есть файл ".env.example", в котором содержутся основные переменные окружения, которые вы должны обязательно заполнить. 

Далее в папку YourDataForConvert добавьте исходные данные. 
А именно:
- emotions.csv
- videos.parquet
- player_starts_train.parquet

Далее открываем консоль в данной дирректории и устанавливаем зависимости. 

### pip install -r requirements.txt

После чего нужно конвертировать все входные файлы с данными.
Для этого запустите файл convert_all_data.py и выберите подходящий для вас вариант загрузки данных (необходимо загрузить все доступные файлы).

#### *выбор файлов добавлен для того, чтобы исключить вариант перезаписи сразу всех файлов, если на одном из них в процессе выполнения конвертации произошел сбой. 

После выполнения всех вышеуказанных действий вы можете запускать основной файл app.py, который и выполнит подбор рекомендаций для конкретного пользователя.

# Уникальность нашего проекта
1. Для построения рекомендаций не используются сторонние пакеты.
2. Использование чистого SQL  для фильтрации данных
3. Использование асинхронности
4. В некоторых местах параллельное выполнение кода
5. Максимальная оптимизация


# Задачи на будущее
1. Информационный перегруз пользователей: множество видео с различными темами и качеством усложняет поиск контента по интересам.
2. Сложность определения индивидуальных предпочтений: алгоритмы рекомендаций должны адаптироваться к уникальным интересам каждого пользователя.
3. Низкая точность рекомендаций: постоянные ошибки в предлагаемых видео могут оттолкнуть пользователей от использования видеохостинга.
4. Ограниченность выбора контента: пользователи могут ограничиваться только существующими категориями и жанрами видео, не имея возможности открыть что-то новое.