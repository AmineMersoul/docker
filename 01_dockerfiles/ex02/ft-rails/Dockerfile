FROM ruby

RUN apt-get update && apt-get install -y mysql-client sqlite3 --no-install-recommends
RUN gem install rails

ENV RAILS_VERSION 5.0.1
ENV RAILS_ENV=development

RUN mkdir -p /opt/app
WORKDIR /opt/app

ONBUILD ADD app /opt/app

ONBUILD RUN bundle install
ONBUILD RUN gem install json -v '1.8.3'
ONBUILD RUN rake db:setup
ONBUILD RUN rake db:seed
#docker build -t ft-rails:on-build .
#docker run -it --rm ft-rails:on-build
