FROM python:3.7-alpine

WORKDIR /usr/src/app
ENV FLASK_APP app.py
ENV FLASK_RUN_HOST 0.0.0.0

ADD requirements.txt /usr/src/app/requirements.txt
COPY requirements.txt requirements.txt
RUN pip install -r requirements.txt

COPY . .
ADD . /usr/src/app

EXPOSE 80

CMD ["python","app.py"]