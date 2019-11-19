# Toy Store
REST API with Flask, SQLAlchemy and Marshmallow

## Dependencies

`Python 3.6` and higher is required.

All dependences are described in `Pipfile`, `Pipfile.lock` and `requirements.txt`.

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

## Installation
Run this commands in your terminal
```bash
sudo apt-get install python3 python3-pip postgresql postgresql-contrib libpq-dev redis-server
cd /var && git clone https://github.com/MrHakimov/toy-store.git
cd toy-store
```

Download dependencies:
```bash
pip install flask flask_sqlalchemy psycopg2-binary gunicorn marshmallow marshmallow-sqlalchemy numpy
```

or

```bash
pip install -r requirements.txt
```

Then create DataBase `api` and new user `manager` with password `apidbpassword`.

```bash
sudo -u postgres psql
create database api;
create user manager with encrypted password 'apidbpassword';
grant all privileges on database api to manager;
\q
```

Then run `python` and create table in data base PostgreSQL:

```bash
$ python
>> from app import db
>> db.create_all()
>> exit()
```

## Server launching
Run command:

```bash
gunicorn -b 0.0.0.0:8080 app:app
```

In `/etc/systemd/system` create file `gunicorn.service` with following contents:

```
[Service]
User=entrant
WorkingDirectory=/var/Yandex-Backend-Test
ExecStart=/usr/bin/gunicorn --bind 0.0.0.0:8080 app:app
ExecReload=/bin/kill -s HUP $MAINPID
ExecStop=/bin/kill -s TERM $MAINPID
PrivateTmp=true

[Install]
WantedBy=multi-user.target
```

Then run following commands:
```bash
sudo systemctl enable gunicorn.service
sudo systemctl start gunicorn.service
 ```
