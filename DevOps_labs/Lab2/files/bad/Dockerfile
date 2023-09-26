FROM ubuntu:latest

MAINTAINER Yarilo Gusev  <yaroslav-gusev-00@mail.ru>

RUN apt-get update && \
	apt-get install -y python3 && \
	apt-get install -y python3-pip && \
	apt-get install -y gunicorn

WORKDIR /app/
COPY . .

RUN python3 -m pip install --no-cache-dir --no-warn-script-location --upgrade pip\
	&& python3 -m pip install --no-cache-dir --no-warn-script-location --user -r requirements.txt

RUN python3 manage.py makemigrations
RUN python3 manage.py migrate

CMD ["/bin/sh", "-c", "python3 -m gunicorn -b 0.0.0.0:80 Docker.wsgi —reload"]

EXPOSE 8000
