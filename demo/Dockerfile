# pull official base image
FROM python:3.7-alpine

# set work directory
WORKDIR /usr/src/app

# set environment variables
ENV PYTHONDONTWRITEBYTECODE 1
ENV PYTHONUNBUFFERED 1

# # install psycopg2 dependencies
RUN apk update && apk add postgresql-dev gcc python3-dev musl-dev make
# RUN apk add --no-cache jpeg-dev zlib-dev
# RUN apk add --no-cache --virtual .build-deps build-base linux-headers


# install dependencies
RUN pip install --upgrade pip
COPY ./requirements.txt /usr/src/app/requirements.txt
RUN pip install -r requirements.txt
# copy project
COPY . /usr/src/app/