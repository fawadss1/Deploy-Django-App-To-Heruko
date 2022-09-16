# Deploy Django App to Heroku
 

## Usage

* If you don't have git installed, follow this [Tutorial](https://www.atlassian.com/git/tutorials/install-git) and come back here.

* [Make a Heroku account](https://signup.heroku.com/)

* [Download Heroku CLI](https://devcenter.heroku.com/articles/heroku-cli)

* [Configure Django Heroku](https://devcenter.heroku.com/articles/django-app-configuration)



* Make a copy of your project or use a seperate git branch.

* Make sure your virtual environment is activated.

```shell
pip install whitenoise
```

* Add this in settings.py
```python
STATIC_ROOT = os.path.join(BASE_DIR, 'staticfiles')
STATICFILES_STORAGE = "whitenoise.storage.CompressedStaticFilesStorage"

MIDDLEWARE = [
    # ...
    "django.middleware.security.SecurityMiddleware",
    "whitenoise.middleware.WhiteNoiseMiddleware",
    # ...
]
```

* Add your dependencies to requirements.txt by typing in the terminal,

```shell
pip freeze > requirements.txt
```
* In your terminal, type in
 ```shell
heroku login
heroku create app_name
git init
heroku git:remote -a app_name
```
Deploy your application
Commit your code to the repository and deploy it to Heroku using Git.
```shell
git add .
git commit -am "First Commit"
git push heroku master
```

```python
DEBUG = False in settings.py
ALLOWED_HOSTS = ['your_app_name.herokuapp.com', 'localhost', '127.0.0.1'] in settings.py
```
* If you make edits, then just type in the terminal,
```shell
git add .
git commit -m "Updated"
git push heroku master
```
