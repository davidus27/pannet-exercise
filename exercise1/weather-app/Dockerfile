# syntax=docker/dockerfile:1

FROM python:3.9-slim-buster

WORKDIR /app

COPY requirements.txt requirements.txt

RUN /usr/local/bin/python -m pip install --upgrade pip

RUN pip3 install -r requirements.txt

COPY getweather .

# CMD [ "python3", "getweather"]

CMD [ "./getweather"]
