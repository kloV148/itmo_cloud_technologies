FROM ubuntu:latest

MAINTAINER Yarilo Gusev  <yaroslav-gusev-00@mail.ru>

RUN apt-get update && \
	apt-get install -y python3 && \
	apt-get install -y python3-pip

WORKDIR /app/
COPY . .

RUN python3 -m pip install --no-cache-dir --no-warn-script-location --upgrade pip\
	&& python3 -m pip install --no-cache-dir --no-warn-script-location --user -r requirements.txt

RUN python3 manage.py makemigrations
RUN python3 manage.py migrate

CMD ["/bin/sh", "-c", "python3 -m gunicorn -b :8000 DockerBad.wsgi --reload"]

#CMD ["gunicorn", "--bind", ":8000", "DockerBad.wsgi"]

EXPOSE 8000