#installing Ruby 1.9.3 and Rails

FROM ubuntu:14.04

MAINTAINER Luis Lavina "https://github.com/chojayr"

RUN apt-get update
RUN apt-get -y install tmux git vim
RUN apt-get -y install ruby1.9.1 ruby1.9.1-dev rubygems1.9.1 irb1.9.1 ri1.9.1
rdoc1.9.1 \
build-essential libopenssl-ruby1.9.1 libssl-dev zlib1g-dev

RUN gem install bundler rails

RUN adduser --disabled-password --home=/rails --gecos "" rails
