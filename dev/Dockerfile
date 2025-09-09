FROM ruby:3.4.5 AS base

RUN apt-get update -qq && apt-get install -y build-essential libpq-dev nodejs apt-utils

WORKDIR /app

RUN gem install bundler

COPY Gemfile* ./

RUN bundle install

COPY . /app

ARG DEFAULT_PORT=3000

EXPOSE ${DEFAULT_PORT}

CMD [ "bundle","exec", "puma", "config.ru"]

