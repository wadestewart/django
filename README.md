## Django
#### Installation (We are following Django Girls tutorial)
1. python3 -m venv myvenv(this is the name of the environment)
2. source myvenv/bin/activate
3. pip install --upgrade pip
4. open code .
5. pip install django~=1.11.0
6. pip install psycopg2
7. django-admin startproject mysite . (the periood matters!)

#### Set up Database
1. Get into PSQL
2. CREATE DATABASE 'name of db';
3. CREATE USER 'username' WITH PASSWORD 'password';
4. GRANT ALL PRIVILEGES ON DATABASE 'name of db' TO 'username';
5. \q
6. Get into your Django environment
7. In the Settings file you will need to update:
```
DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.postgresql_psycopg2', (adding Postgresql)
        'NAME': 'name of db',
        'USER': 'username',
        'PASSWORD': 'password',
        'HOST': 'localhost'
    }
}
```
8. In the Settings file you will also need to update:
```
INSTALLED_APPS = [
    'django.contrib.admin',
    'django.contrib.auth',
    'django.contrib.contenttypes',
    'django.contrib.sessions',
    'django.contrib.messages',
    'django.contrib.staticfiles',
    'app_name'
]
```

#### Start your server
1. Run the comnmand ``python manage.py runserver`` in your Django environment.
You're up and running!

#### Models
1. Define fields that will be columns in your database, for example:
```
class Artist(models.Model):
    name = models.CharField(max_length=100)
    nationality = models.CharField(max_length=100)
```
2. This method will set default for an instance of the model
```
def __str__(self):
        return self.name
```
3. Generate migration files with ``python manage.py makemigrations``
4. Commit migration to database with ``python manage.py migrate``

