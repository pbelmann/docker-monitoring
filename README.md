## Docker Monitoring Grafana Dashboard

The following descriptions and instructions are based on the [Docker Monitoring Article](https://www.brianchristner.io/how-to-setup-docker-monitoring/).
Instructions in this document allow to to create the following Dashboard:
![Docker Grafana Monioring Dashboard](https://raw.githubusercontent.com/vegasbrianc/docker-monitoring/master/Docker_Monitoring.png)


### Install

The installation is based on three docker images: [cadvisor](https://github.com/google/cadvisor), [influxdb](https://github.com/influxdb/influxdb), [grafana](http://grafana.org/) that are created and linked with [docker compose](https://github.com/docker/compose).

1. Install docker compose explained on the docker [releases page](https://github.com/docker/compose/releases). 
2. Restart the docker service: `sudo service docker restart`
3. Download the project and start the container:

~~~bash 
git clone https://github.com/pbelmann/docker-monitoring.git &&
cd docker-monitoring &&
sudo docker-compose up
~~~

Each of the applications is active now which can be verified with the browser:

* cadvisor: http://localhost:8080
* influxdb: http://localhost:8083
* grafana: http://localhost:3000
