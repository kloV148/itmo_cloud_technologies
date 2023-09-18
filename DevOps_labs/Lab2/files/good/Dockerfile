FROM python:3.11.5-bookworm

MAINTAINER Ivan Skvorcov <mainoistskvorcov@gmail.com>

WORKDIR usr/src/app

RUN pip install --upgrade pip
COPY ./requirements.txt .
RUN pip install -r requirements.txt
COPY . /usr/src/app

EXPOSE 8000
CMD ["/bin/sh", "-c", "python3 -m gunicorn -b 0.0.0.0:80 Docker.wsgi --reload"]

