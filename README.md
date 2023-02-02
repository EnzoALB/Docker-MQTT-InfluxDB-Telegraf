# Docker MQTT - InfluxDBv2 - Telegraf

## Prérequis 

- Docker
- Docker-compose

## Commandes 


- `docker-compose up -d` va utiliser `docker-compose.yml` pour lancer les dockers MQTT, influxDB et Telegraf.
- `docker ps` liste les dockers

Pour tester MQTT: 
- `docker exec -it mqtt-influxdb-telegraf_mqtt_1 /bin/sh` Va ouvrir un terminal dans le container,
- `mosquitto_pub -h localhost -p 1883 -t "test" -m "0"` Va publier 0 sur le topic test.

dans un navigateur : http://[hostip]:8086 
user : admin
password : adminadminadmin de base.  

## Docker-compose.yml

Pour modifier les crédentials et les topics a écouter c'est: 

Dans `dockermqtt/conf/telegraf.conf.docker` On va changer les logins par ce qu'on veut, penser aussi a modifier la ligne `entrypoint` dans `docker-compose.yml` pour changer les logins.

Pour changer les topics :

Dans `dockermqtt/conf/telegraf.conf.docker` dans topics on ajoute les topics voulu. 
# Lorax
