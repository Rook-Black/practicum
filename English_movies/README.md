# Описание проекта

Школа английского языка Яндекс Практикум хочет получить модель которая сможет по субтитрам к фильму определять его уровень по классификации CEFR.


В данной работе необходимо:

- Обрработать субтитры к фильмам и подготовить их для обучения модели.
- Обучить модель и получить приемлимую метрику accuracy.
- Упаковать модель в необходимом виде и предоставить заказчику.

# Используемые библиотеки

- pandas 
- pysrt
- streamlit
- os
- re
- bs4
- datetime 
- unicodedata
- spacy
- pypdf 
- sklearn
- catboost 
- copy

# Что было проделано

1. Первоночальный просмотр данных
2. Приведение названия субтитров и фильмов к единому виду
3. Парсинг субтитров оставшихся без фильмов
4. Удаление дубликатов
5. Приведение уровня языка к единому формату
6. Оценка распределения количества фильмов по уровням  
![levels](https://github.com/Rook-Black/Practicum/assets/108406912/f46eae7c-3bd3-48d5-afba-4f32abac9291)  
7. Большая предобработка субтитров.  
  a. Перевод субтитров из формата srt в txt и делим их на 10 частей для увелечения выборки  
  b. Параллено убираю лишние строки и символы из субтитров  
  с. Считаю количество слов и время для каждого файла  
  d. Так же посчет среднего количество слов в секунду  
  Предварительный результат   
  ![table](https://github.com/Rook-Black/Practicum/assets/108406912/27fd8038-0eed-40a6-93aa-5396102e40c4)  
  e. Обработка самого текста субтитров лемитизация и удаление стоп слов  
  f. Подсчет уникальных слов, слов разного уровня и их отношение ко всем словам.  
  Итоговая таблица
  ![final_table](https://github.com/Rook-Black/Practicum/assets/108406912/1ca7eef5-14a8-46b8-987a-c13243c83a1f)  
8. Масштабирование и кодирование
9. Обучение моделей и оценка важности фичей
10. Создание скрипта для обработки субтитров и выдачи предсказания
11. Использование streamlit для создания интерфейса
12. Упаковка в докер [DockerHub](https://hub.docker.com/layers/rookblack/masterskaja/film_level_determiner/images/sha256-62cd07f4abe74fdc6b0961fe622c244a4fffc33a2edf8b32ff91a4b785017818?context=repo)

# Результаты

Получили модель которая может с точностью 0.75 предсказывать сложность фильма, проект имеет полноценный интерфейс и все упаковано в Docker
