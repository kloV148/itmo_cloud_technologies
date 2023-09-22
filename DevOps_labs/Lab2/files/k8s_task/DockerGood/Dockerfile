FROM python:3.11.5-bookworm

MAINTAINER Ivan Skvorcov <mainoistskvorcov@gmail.com>

WORKDIR usr/src/app

RUN pip install --upgrade pip
COPY ./requirements.txt .
RUN pip install -r requirements.txt
COPY . /usr/src/app

EXPOSE 8000
CMD ["gunicorn", "--bind", ":8000", "DockerGood.wsgi"]