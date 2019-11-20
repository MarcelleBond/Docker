FROM ruby
RUN apt-get update
RUN apt-get install sqlite3 -y
RUN /bin/bash -l -c "gem install rails"
RUN apt-get install nodejs -y
RUN apt-get update
RUN apt-get install yarn -y
RUN rails new app
ADD https://raw.githubusercontent.com/rails/webpacker/master/lib/install/config/webpacker.yml app/config/
RUN mv app opt/
WORKDIR opt/app
EXPOSE 3000
RUN bundle install
RUN rake db:migrate
RUN rake db:seed