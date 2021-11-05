FROM ruby:3.0.1-slim-buster

RUN apt-get update && \
      apt-get install -y -qq build-essential unzip curl postgresql libpq-dev

RUN curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip" && \
  unzip awscliv2.zip && \
  ./aws/install

COPY Gemfile .
RUN gem install bundler && bundle install -j `nproc --all`

CMD bash
