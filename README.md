# Рандомайзер фильмов 
Выдаёт рандомный фильм из бд(есть 20 шт, остальное либо выгружать руками, либо cvs файликом как в репе).
Есть некоторая база фильмов(файл cvs), есть ручки для добавления, есть фронт на html, css, есть апишка, есть функция загрузки. 
Запускай и пользуйся.
### Стек
- python, flask
- sqlalchemy, alembic, cvs
- html

### Как запустить проект:
Создайте .env файл, например:
```
FLASK_APP=opinions_app
FLASK_ENV=development
DATABASE_URI=sqlite:///C:\dev\Good_movie_to_watch\opinions_app\db.sqlite3
SECRET_KEY=YOUR_SECRET_KEY
```
Клонировать репозиторий и перейти в него в командной строке:
```
git clone git@github.com:YaroslavSmrinov/Good_movie_to_watch.git
cd what_to_watch
```
Cоздать и активировать виртуальное окружение:
```
python3 -m venv venv
source venv/bin/activate
```
или для пользователей Windows
```
source venv/Scripts/activate
```
Установить зависимости из файла requirements.txt:
```
python3 -m pip install --upgrade pip
pip install -r requirements.txt
```
Создайте бд
```
flask shell
>>> from opinions_app import db
>>> db.create_all()
>>>exit()
```
Наполните бд фильмами из cvs (там всего 20 шт.)
```
flask load_opinions
```
Запускайте 
```
flask run
```