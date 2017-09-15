# Heroku Django Deployments

To deploy on Heroku, you will need to create the following files: `requirements.txt`, `runtime.txt` and `Procfile`. You will also need to modify your `settings.py` and `wsgi.py` files.

## requirements.txt

First install all of the following:

```
$ pip install gunicorn
$ pip install dj-database-url
$ pip install psycopg2
$ pip install whitenoise
```

Then use `$ pip freeze > requirements.txt` to create your requirements.txt file:

```
certifi==2017.4.17
chardet==3.0.4
dj-database-url==0.4.2
Django==1.11.2
gunicorn==19.7.1
idna==2.5
psycopg2==2.7.1
pytz==2017.2
requests==2.18.1
urllib3==1.21.1
whitenoise==3.3.0

```

## runtime.txt

Create a runtime.txt file that contains just one line indicating the version of Python you are using. To get your exact version of Python use the command `$ python -V`.

runtime.txt:

```
python-3.6.1
```

## Procfile

Create a file called Procfile (no extension) that tells Heroku to start and run your app with Gunicorn:

```
web: gunicorn djangoprojectnamehere.wsgi --log-file -
```

## settings.py

First, create your Heroku app so that you can push environment variables to Heroku during setup:
```
$ heroku create appnamehere
```

Get security key from Heroku environment variables, set default for local development:

```python
# SECURITY WARNING: keep the secret key used in production secret!
SECRET_KEY = os.environ.get('DJANGO_SECRET_KEY', 'secretkeygoeshere')
```

And set the secret key variable on Heroku using the command:

`$ heroku config:set DJANGO_SECRET_KEY=secretkeygoeshere`

Set debug to False for production, True for local development:

```python
# SECURITY WARNING: don't run with debug turned on in production!
DEBUG = bool(os.environ.get('DJANGO_DEBUG', True))
```

Then on Heroku, set the debug environment variable to the empty string:

`$ heroku config:set DJANGO_DEBUG=''`

To take advantage of Heroku's free / auto-managed SSL certificates, add the following. This will redirect all users to https:

```python
# Honor the 'X-Forwarded-Proto' header for request.is_secure()
SECURE_PROXY_SSL_HEADER = ('HTTP_X_FORWARDED_PROTO', 'https')
SECURE_SSL_REDIRECT = bool(os.environ.get('DJANGO_SSL_REDIRECT', False))
```

Then set a Heroku DJANGO_SSL_REDIRECT environment variable to True:

`$ heroku config:set DJANGO_SSL_REDIRECT=True`

Modify allowed hosts to include your domain name, app name, and localhost:

`ALLOWED_HOSTS = ['domainnamehere.com', 'appnamehere.herokuapp.com', '127.0.0.1']`

Get database URL from Heroku auto-created Postgres install:

```python
import dj_database_url

# Heroku: Update database configuration from $DATABASE_URL.
db_from_env = dj_database_url.config(conn_max_age=500)
DATABASES['default'].update(db_from_env)
```

Don't forget to set your timezone!

`TIME_ZONE = 'America/Los_Angeles'`

Finally for static file serving, implement the following: 

```python
# Static files (CSS, JavaScript, Images)
# https://docs.djangoproject.com/en/1.10/howto/static-files/

# The absolute path to the directory where collectstatic will collect static files for deployment.
STATIC_ROOT = os.path.join(BASE_DIR, 'staticfiles')

# The URL to use when referring to static files (where they will be served from)
STATIC_URL = '/static/'

# Simplified static file serving.
# https://warehouse.python.org/project/whitenoise/
STATICFILES_STORAGE = 'whitenoise.django.GzipManifestStaticFilesStorage'
```

To add additional logging for collectstatic push the following to Heroku:
```
$ heroku config:set DEBUG_COLLECTSTATIC=1
```

## wsgi.py

Finally, modify your wsgi.py to the following:

```python
import os

from django.core.wsgi import get_wsgi_application
from whitenoise.django import DjangoWhiteNoise

os.environ.setdefault("DJANGO_SETTINGS_MODULE", "djangoprojectnamehere.settings")


application = get_wsgi_application()
application = DjangoWhiteNoise(application)
```

## Push / Deploy

Commit changes:

```
$ git add .
$ git commit -m 'Deployment settings'
$ git push origin master
```

Push to Heroku:

```
$ git push heroku master
```

Run migrations, create superuser, and open your live app:

```
$ heroku run python manage.py migrate
$ heroku run python manage.py createsuperuser
$ heroku open
```



