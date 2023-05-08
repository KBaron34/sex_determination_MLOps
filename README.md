# Описание задачи

Ссылка на данные: https://ods.ai/competitions/mtsmlcup

Можно ли составить хотя бы приблизительное представление о человеке, обладая информацией о сайтах, 
которые он посещает? Можно ли по таким цифровым следам пользователя 
(на каких сайтах с каких IP он сидел, сколько раз заходил, какое у него устройство) понять, кто этот пользователь? 
Мужчина или женщина? 

Действительно, в Digital-рекламе часто сегмент включает себя пол. 
Эта задача особенно актуальна для рекламных DSP-площадок, 
которые в OpenRTB запросах получают такие данные с частотой 200 000 запросов в секунду со всех сайтов, 
размещающих рекламу за деньги.

Задача: предсказать пол пользователя по его цифровым следам.

Описание данных:
- region_name – Регион;
- city_name – Населенный пункт;
- cpe_manufacturer_name – Производитель устройства;
- cpe_model_name – Модель устройства;
- url_host – Домен, с которого пришел рекламный запрос;
- cpe_type_cd – Тип устройства (смартфон или что-то другое);
- cpe_model_os_type – Операционка на устройстве;
- price – Оценка цены устройства;
- date – Дата;
- part_of_day – Время дня (утро, вечер, итд);
- request_cnt – Число запросов одного пользователя за время дня (поле part_of_day);
- user_id – ID пользователя;
- age – Возраст пользователя;
- is_male – Пол пользователя : мужчина (1-Да, 0-Нет).

Target - is_male.

## Основные команды для запуска FastAPI

- Запуск приложения из папки backend

`cd backend`

`uvicorn main:app --host=0.0.0.0 --port=8000 --reload`

Доступ к сервису FastAPI http://localhost:8000/docs

___

## Основные команды для запуска Streamlit

Обязательно запускаем frontend чась проекта, только после запуска backend  в отдельном терминале

- Команда в отдельном теминале для запуска приложения Streamlit

`cd frontend`

`streamlit run main.py`

Приложение будет доступно по адресу http://localhost:8501 

Если хотите запустить по конкретному порту, например 8080, то:

`streamlit run main.py --server.port 8080`

___

## Folders
- `/backend` - Папка с проектом FastAPI
- `/frontend` - Папка с проектом Streamlit
- `/config` - Папка, содержащая конфигурационный файл
- `/data` - Папка, содержащая исходные данные, обработанные данные, уникальные значения в формате JSON, als модель, 
            а также неразмеченный файл для подачи на вход модели
- `/models` - Папка, содержащая сохраненную модель после тренировки
- `/notebooks` - Папка, содержащая jupyter ноутбуки с предварительным анализом данных
- `/report` - Папка, содержащая информацию о лучших параметрах и метриках после обучения
