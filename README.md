# recipe-app-api
Recipe app api source code

Dockerfile
requirements.txt

$ sudo docker build .

docker-compose.yml

$ sudo docker-compose build

$ sudo docker-compose run app sh -c "django-admin.py startproject app ."

Travis-ci.org
.travis.yml

$ sudo docker-compose run app sh -c "python manage.py test" && flake8

#### Core app

$ sudo docker-compose run app sh -c "django-admin.py startapp core"
clean
  test.py(all test in a folder test)
  views.py(core don't serve anything just hold database models)
new
    tests/
      __init__.py

create models:
  tests/test_models.py
  in models.py create user Model
  app/settings at the end
    AUTH_USER_MODEL = 'core.User'

$ sudo docker-compose run app sh -c "python manage.py makemigrations core"

POSTEGRES
  edit docker-compose.yml
  edit requirements.txt
  edit Dockerfile
  $ sudo docker-compose build
  update DATABASE settings.py

  hepler to verify db is up before django try to connect
    test_commands.py
    management/commands/wait_for_db.py
