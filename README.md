# Docker

Домашнее задание

1 Установите Docker на хост машину

2 Установите Docker Compose - как плагин, или как отдельное приложение

3 Создайте свой кастомный образ nginx на базе alpine. После запуска nginx должен отдавать кастомную страницу (достаточно изменить дефолтную страницу nginx)

4 Определите разницу между контейнером и образом

5 Вывод опишите в домашнем задании.
	
   `Образ - это шаблон для создания Docker-контейнеров.`
	
   `Контейнер - это стандартная единица программного обеспечения, в которую упаковано приложение со всеми зависимостями.`

6 Ответьте на вопрос: Можно ли в контейнере собрать ядро?
	
   `Нет нельзя - docker контейнер не имеет своего ядра и запускается используя ядро хостовой системы.`

7 Собранный образ необходимо запушить в docker hub и дать ссылку на ваш репозиторий.
	
   `https://hub.docker.com/repository/docker/nikpuskov/nginx_alpine`

Стенд на Vagrant с боксом ubuntu/jammy64 с установкой Docker, установкой плагина Docker-compose, созданием Docker-образа и запуском Docker-контейнера 

(Vagrantfile, Dockerfile и измененная дефолтная страница Nginx прилагается)

`vagrant up`

`vagrant ssh`

`curl localhost`

Пуш образа в docker hub

`sudo docker login -u nikpuskov`

`enter password`

`sudo docker tag alpine nikpuskov/nginx_alpine:alpine`

`sudo docker push nikpuskov/nginx_alpine:alpine`
