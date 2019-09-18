FROM ubuntu:18.04
LABEL maintaner="Alikhan M. (alikhan.murzayev@gmail.com)"
ENV LC_ALL C.UTF-8
ENV LANG C.UTF-8
# install python3.7 and pip3
RUN apt-get update && apt-get install -y \
    python3.7-dev \
    python3-pip \
# Essential tools and xvfb
RUN apt-get update && apt-get install -y \
    software-properties-common \
    unzip \
    curl \
    xvfb \
    wget
# install firefox browser
RUN apt-get update && apt-get install -y \
    firefox
# Gecko Driver
ENV GECKODRIVER_VERSION 0.23.0
RUN wget --no-verbose -O /tmp/geckodriver.tar.gz https://github.com/mozilla/geckodriver/releases/download/v$GECKODRIVER_VERSION/geckodriver-v$GECKODRIVER_VERSION-linux64.tar.gz \
  && rm -rf /opt/geckodriver \
  && tar -C /opt -zxf /tmp/geckodriver.tar.gz \
  && rm /tmp/geckodriver.tar.gz \
  && mv /opt/geckodriver /opt/geckodriver-$GECKODRIVER_VERSION \
  && chmod 755 /opt/geckodriver-$GECKODRIVER_VERSION \
  && ln -fs /opt/geckodriver-$GECKODRIVER_VERSION /usr/bin/geckodriver \
  && ln -fs /opt/geckodriver-$GECKODRIVER_VERSION /usr/bin/wires
