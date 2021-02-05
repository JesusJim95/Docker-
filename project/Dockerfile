FROM ruby:2.5.1

RUN apt-get update -q && apt-get install -y vim build-essential libpq-dev curl
RUN curl -sL https://deb.nodesource.com/setup_11.x  | bash -
RUN apt-get -y install nodejs

#Crear directorio y espacio de trabajo
COPY ./qa /app

WORKDIR /app

#Instalar gemas y servicio necesario para ejecutar la app
RUN bundle install

#Install npm 
WORKDIR /app/client
RUN npm install
#Especifca entorno en el que se desplegará
ENV RAILS_ENV=production
#Master key 
ENV RAILS_MASTER_KEY=ef4f45a824cb3b7fce877a40a2ad466b
#ejecutar app
WORKDIR /app
CMD bundle exec unicorn -c config/unicorn.rb
