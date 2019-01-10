# Home Server with lots of nice things

## Install

1. Install Docker
2. Install `docker-compose`
3. Create lots of directories 
```sh
sudo mkdir /var/pihole
```
1. Set a pihole
   1. `ssh` into PI
   2. `docker exec -it pihole_container_name pihole -a -p`
   3. Enter new password twice
   4. Set up via web portal at `<pi-ip>/admin`

## Run
To run all components, go to the directory and run 

```sh
docker-compose up -d
```

## Shut Down
To shut down all running docker containers, you can run

```sh
docker stop $(docker ps -a -q)
```

## Components

| Name      | Description                             | Link                                                        | Port/Credentials       |
| --------- | --------------------------------------- | ----------------------------------------------------------- | ---------------------- |
| openHAB   |                                         | <https://www.openhab.org/>                                  | 8080                   |
| grafana   | Time Series Analytics and Visualization | <https://grafana.com/>                                      | 3000 admin/admin       |
| influxDB  | Time Series Storage                     | <https://www.influxdata.com/time-series-platform/influxdb/> | 8080 db:iot / password |
| mosquitto | MQTT Broker                             | <https://mosquitto.org/>                                    | 9001                   |