FROM rails:4.2

MAINTAINER matwu matwumatwu@gmail.com

# install vim to edit rails modules
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

EXPOSE 8080

# start server
CMD ["/bin/bash"]
