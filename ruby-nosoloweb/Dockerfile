FROM ruby:2.3.1

RUN apt-get update -q && apt-get install -y build-essential libpq-dev nodejs curl
#Crear directorio y espacio de trabajo
COPY ./nosoloweb /app

WORKDIR /app

#Instalar gemas y servicio necesario para ejecutar la app
RUN bundle install
#Especifca entorno en el que se desplegará
ENV RAILS_ENV=production
ENV SECRET=32fnh9283nf92nf928nf29 

#Exponer puerto
EXPOSE 8080

#Ejecutrar app
CMD bundle exec unicorn -c config/unicorn.rb
