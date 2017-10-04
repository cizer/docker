FROM ubuntu:trusty
MAINTAINER Richie Mackay "richie.mackay@gmail.com"

RUN apt-get -y update && \
    apt-get install -y -q \
    unzip \
    curl \
    git \
    python

RUN curl -kL https://bootstrap.pypa.io/get-pip.py | python
RUN pip install awsebcli --upgrade

ENV HOME=/home
COPY .aws* /home/.aws
WORKDIR /env

ENTRYPOINT ["eb"]
CMD ["--version"]