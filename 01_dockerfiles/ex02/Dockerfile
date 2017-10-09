FROM ruby

RUN apt-get update -y && apt-get upgrade -y && \
	apt-get install nodejs -y && gem install rails bundler && mkdir -p /opt/app

ONBUILD COPY . /opt/app
ONBUILD WORKDIR /opt/app
ONBUILD EXPOSE 3000
ONBUILD RUN bundle install && rake db:migrate && rake db:seed
