# syntax=docker/dockerfile:1

FROM python:3.9-slim-buster

WORKDIR /app

COPY Pipfile Pipfile
COPY Pipfile.lock Pipfile.lock
RUN python3 -m pip install --upgrade pip
RUN pip install pipenv
RUN pipenv install --system --deploy --ignore-pipfile

COPY . .

ENV FLASK_APP=src/app
CMD [ "python3", "-m" , "flask", "run", "--host=0.0.0.0"]