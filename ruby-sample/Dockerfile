FROM ruby:2.6.3

#Dependencias y paquetes necesarios
RUN apt-get update -q && apt-get install -y build-essential libpq-dev nodejs curl
RUN apt-get install -qy nginx && apt-get install -y yarn

#Crear directorio y espacio de trabajo
COPY ./ruby-rails-sample /app
WORKDIR /app
COPY ./conf_sampleruby /etc/nginx/sites-enabled/

#Instalar gemas y servicio necesario para ejecutar la app
RUN bundle
RUN curl https://cli-assets.heroku.com/install-ubuntu.sh | sh

#Especifca entorno en el que se desplegará
ENV RAILS_ENV development


#Exponer puerto
EXPOSE 8080

#Ejecutrar app
CMD bundle exec rake bootstrap && heroku local

