FROM alpine
MAINTAINER munkyshi22@gmail.com

ENV TZ=America/Los_Angeles
ENV LC_ALL=en_US.UTF-8
ENV LANG=en_US.UTF-8
ENV LANGUAGE=en_US.UTF-8

RUN apk update && apk upgrade
RUN apk add bash
RUN addgroup -g 1000 munky
RUN adduser -S -h /home/munky -s /bin/bash -G munky -D -u 1000 munky

RUN apk add python3
WORKDIR /tmp
RUN wget https://bootstrap.pypa.io/get-pip.py
RUN python3 get-pip.py
RUN rm -f git-pip.py
RUN pip3 install --upgrade pip

# set up StONE applications
RUN mkdir -p /home/munky/logs
WORKDIR /home/munky
RUN chown -R munky:munky /home/munky

USER munky
