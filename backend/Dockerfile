FROM python:3.6-alpine

RUN apk update && apk add gcc g++ make libffi-dev openssl-dev git
RUN pip install --upgrade pip setuptools tox

ENV WORKDIR "/opt/app"

RUN mkdir -p $WORKDIR
WORKDIR $WORKDIR

COPY activate $WORKDIR/activate
COPY tox.ini $WORKDIR/tox.ini
COPY requirements.txt $WORKDIR/requirements.txt

RUN TOXBUILD=true tox
