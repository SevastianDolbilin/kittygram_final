# Kittygram

Kittygram — социальная сеть для обмена фотографиями любимых питомцев. В рамках проекта была реализована автоматизация развертывания, что упростило процесс доставки и поддержки приложения.

## Основная функциональность проекта
- Публикация фотографий с описанием
- Возможность оставлять комментарии
- Авторизация и управление пользователями
- Фильтрация и сортировка изображений
- Полностью работающий API
- Полностью работающая админ-панель


## Мой вклад в проект
- Настроил процесс автоматического развертывания с использованием Docker и CI/CD.
- Интегрировал GitHub Actions для автоматического тестирования и деплоя.
- Контейнеризировал приложение с помощью Docker, упростив его развертывание в разных средах.
- Настроил развертывание фронтенда, обеспечив его интеграцию с бэкендом.
- Разработал и настроил workflow для GitHub Actions, автоматизировав процесс тестирования и деплоя.



## Роли пользователей
В проекте предусмотрены 4 роли пользователей:

1. Анонимный пользователь
    - Может просматривать фотографии и профили авторов постов.
    - Не может публиковать фотографии и оставлять комментарии.

2. Зарегистрированный пользователь:
    - Может просматривать чужие и собственные фотографии.
    - Может просматривать профили авторов фотографий.
    - Может публиковать собственные фотографии.

3. Автор:
    - Все возможности зарегистрированного пользователя.
    - Может удалять и редактировать свои посты с фотографиями.

4. Администратор:
    - Полный доступ ко всем функциям проекта.
    - Управление пользователями, постами и категориями.

## Используемые технологии
- Python 3.9
- Django REST Framework
- PostgreSQL
- Pillow
- Pytest
- flake8
- React


## Автоматическое развертывание
1. Настроены GitHub Actions для автоматического запуска тестов и деплоя при пуше в main.
2. Контейнеризация приложения позволяет развернуть его в разных окружениях без дополнительных настроек.
3. После успешного деплоя отправляется уведомление в Telegram через бота.

## Запуск проекта локально
1. Клонирование репозитория
```bash
git clone https://github.com/your-repo.git
cd your-repo
```
2. Создание и активация виртуального окружения
   
    python -m venv venv

    # Windows
    venv\Scripts\activate

    # Linux/MacOS
    source venv/bin/activate

4. Установка зависимостей
   
    pip install -r requirements.txt

5. Применение миграций и создание суперпользователя
   
    cd backend
    python manage.py migrate
    python manage.py createsuperuser

6. Локальное развертывание проекта
   
    python manage.py runserver

7. Запуск Фронтенда
   
    cd frontend
    npm install
    npm start


## Развертывание проекта на удаленном сервере
1. Клонирование репозитория
```bash
git clone https://github.com/your-repo.git
cd your-repo
```
2. Запуск контейнеров
```bash
docker-compose up -d
```

3. Применение миграций и создание суперпользователя
   
    docker exec -it kittygram_backend python manage.py migrate
    docker exec -it kittygram_backend python manage.py createsuperuser

5. Сборка статических файлов
   
    docker exec -it kittygram_backend python manage.py collectstatic --noinput
    После выполнения всех шагов проект будет готов к использованию.
