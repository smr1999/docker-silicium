FROM python:alpine

RUN mkdir /app

WORKDIR /app

COPY ./app.py .

RUN pip install --upgrade pip 

RUN pip install flask gunicorn

CMD gunicorn -b 0.0.0.0:5000 app:app 
# first app is name of flask app and second app is name of gunicorn app

