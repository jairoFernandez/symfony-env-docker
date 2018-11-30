## Create a environment for dev in Symfony 4 projects


1. Download the env
```sh
wget http://github.com/jairoFernandez/symfony-env-docker/archive/master.zip && unzip master.zip -d my_awesome_symfony_project
```

2. Build a image
```sh
cd my_awesome_symfony_project
docker-compose build
docker-compose up -d
```

## MySql container
```sh
docker exec -it -u sf4_mysql bash
```

## PHP container
```sh
docker exec -it -u dev sf4_php bash
```
Inside the container run `cd /home/wwwroot/sf4`

And create your symfony 4 project
```sh
composer create-project symfony/skeleton my-temp-folder
cp -Rf /home/wwwroot/sf4/my-temp-folder/. .
rm -Rf /home/wwwroot/sf4/my-temp-folder
```

*** This project is a copy of ***
[https://github.com/romaricp/kit-starter-symfony-4-docker](https://github.com/romaricp/kit-starter-symfony-4-docker) :heart:

PD: When you configure the url of your db connection in symfony, the host is the name of container 'sf4_mysql'

`DATABASE_URL=mysql://sf4:sf4@sf4_mysql:3306/sf4`