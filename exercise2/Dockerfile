# syntax=docker/dockerfile:1

FROM python:3.9-slim-buster


WORKDIR /app

COPY requirements.txt requirements.txt

RUN /usr/local/bin/python -m pip install --upgrade pip

RUN apt update

RUN apt install -y nmap

RUN pip3 install -r requirements.txt


COPY scanner .


CMD [ "./scanner" ]
