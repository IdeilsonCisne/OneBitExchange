# README

Como esse projeto foi criado, executando os seguintes comandos:

* docker run --rm --user "$(id -u):$(id -g)" -v $(pwd):/usr/src -w /usr/src -ti ruby:2.5.1 bash
* gem install rails -v 5.2
* rails new OneBitExchange --database=postgresql --skip-bundle
* exit
* cd OneBitExchange
* docker-compose build

## Para criar db, migrações e rodar o projeto.

* docker-compose run --rm app bundle install
* docker-compose run --rm app bundle exec rails db:create db:migrate
* docker-compose up

## Para logar na máquina docker
* docker-compose run --rm app bash

## Para editar o arquivo credencial
* EDITOR=nano bundle exec rails credentials:edit

## Para instalar jQuery e Bootstrap via yarn
* docker-compose run --rm app bundle exec yarn add jquery
* docker-compose run --rm app bundle exec yarn add bootstrap

## Para consertar problema de permissão do docker
* sudo chown $USER:$USER -R .

## Para realizar testes rspec
* docker-compose run --rm app bundle exec rspec spec/services/exchange_service_spec.rb
* docker-compose run --rm app bundle exec rspec spec/requests/exchanges_spec.rb
* docker-compose run --rm app bundle exec rspec spec/system/exchanges_index_system_spec.rb

## Para acessar o console
* docker-compose run --rm app bundle exec rails c

## Para criar controller com actions
* docker-compose run --rm app bundle exec rails g controller Exchanges index convert --no-controller-specs

## Para gerar testes com rspec
* docker-compose run --rm app bundle exec rails g rspec:request exchanges

## Para testar via browser chamada API
* http://localhost:3000/convert?source_currency=BRL&target_currency=EUR&amount=10

## Para deploy
* Efetuar commit no repositório.
