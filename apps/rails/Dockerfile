FROM ruby:2.2

MAINTAINER matwu matwumatwu@gmail.com

RUN apt-get update -qq && apt-get install -y build-essential

# for postgres
RUN apt-get install -y libpq-dev

# for nokogiri
RUN apt-get install -y libxml2-dev libxslt1-dev

# for capybara-webkit
RUN apt-get install -y libqt4-webkit libqt4-dev xvfb

# for a JS runtime
RUN apt-get install -y nodejs

# for editing
RUN apt-get install -y vim

# create working directory
ENV APP_HOME /app
RUN mkdir $APP_HOME
WORKDIR $APP_HOME

# initialize git
RUN git config --global user.name matwu
RUN git config --global user.email matwumatwu@gmail.com

# clone rails app from github
RUN git clone https://github.com/matwu/rails-api.git $APP_HOME
RUN bundle update

# Expose ports.
EXPOSE 3000
