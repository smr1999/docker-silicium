FROM python:alpine

#Do not create pyc
ENV PYTHONDONTWRITEBYTECODE 1
#Handle input output
ENV PYTHONUNBFFERED 1
ENV DJANGO_SUPERUSER_PASSWORD admin

RUN mkdir /app
WORKDIR /app

# To use mysqlclient
RUN apk update
RUN apk add --no-cache gcc python3-dev musl-dev mariadb-dev

RUN pip install --upgrade pip
RUN pip install django gunicorn mysqlclient

# because mariadb-dev just install with these dependencies
RUN apk del gcc python3-dev musl-dev

CMD python3 manage.py makemigrations --noinput && \
    while ! python3 manage.py migrate --noinput > /dev/null 2>&1 ; do sleep 1 ; done && \
    python3 manage.py createsuperuser --user admin --email admin@gmail.com --noinput; \
    gunicorn -b 0.0.0.0:8000 app.wsgi


