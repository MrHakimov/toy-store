# Toy Store
REST API with Flask, SQLAlchemy and Marshmallow

## Dependences

The app requires `Python 3.6` and higher

All dependences are described at `Pipfile`, `Pipfile.lock` and also at `requirements.txt`.

```
Click==7.0
Flask==1.1.1
flask-marshmallow==0.10.1
Flask-SQLAlchemy==2.4.0
gunicorn==19.9.0
itsdangerous==1.1.0
Jinja2==2.10.1
MarkupSafe==1.1.1
marshmallow==3.0.1
marshmallow-sqlalchemy==0.17.0
numpy==1.17.0
psycopg2==2.8.3
redis==3.3.8
simplejson==3.16.0
six==1.12.0
SQLAlchemy==1.3.7
Werkzeug==0.15.5
```

## Installing
Run this commands at your terminal
```
sudo apt-get install python3 python3-pip postgresql postgresql-contrib libpq-dev redis-server
cd /var && git clone https://github.com/kholmatov/Yandex-Backend-Test.git
cd Yandex-Backend-Test
```

Downloading denpendences:
```
pip install flask flask_sqlalchemy psycopg2-binary gunicorn marshmallow marshmallow-sqlalchemy numpy
```

or

```pip install -r requirements.txt```
