FROM python:3.10

ENV PYTHONUNBUFFERED 1
ENV PYTHONDONTWRITEBYTECODE 1

RUN set -e; \
    apt-get update ;\
    apt-get -y upgrade ;\
    apt-get -y install netcat ;\
    apt-get -y install gettext ;

RUN mkdir /code
COPY . /code/
WORKDIR /code

RUN set -e; \
    python3 -m pip install --upgrade pip ;\
    python3 -m pip install -r /code/requirements.txt ;\
    chmod +x /code/docker/entrypoints/entrypoint.sh ;

EXPOSE 8000
ENTRYPOINT ["/code/docker/entrypoints/entrypoint.sh"]