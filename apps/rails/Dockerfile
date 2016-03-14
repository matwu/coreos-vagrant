FROM rails:4.2

MAINTAINER matwu matwumatwu@gmail.com

# see update.sh for why all "apt-get install"s have to stay as one long line
RUN apt-get update && apt-get install -y vim && rm -rf /var/lib/apt/lists/*

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
