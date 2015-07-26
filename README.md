## Docker Monitoring Grafana Dashboard

The following descriptions and instructions are based on the [Docker Monitoring Article](https://www.brianchristner.io/how-to-setup-docker-monitoring/).
Instructions in this document allow to to create the following Dashboard:
![Docker Grafana Monioring Dashboard](https://raw.githubusercontent.com/vegasbrianc/docker-monitoring/master/Docker_Monitoring.png)


### Installation

The installation is based on three docker images: [cadvisor](https://github.com/google/cadvisor), [influxdb](https://github.com/influxdb/influxdb), [grafana](http://grafana.org/) that are created and linked with [docker compose](https://github.com/docker/compose).

1. Install docker compose as explained on the docker compose [releases page](https://github.com/docker/compose/releases). 
2. Restart the docker service: `sudo service docker restart`
3. Download the project and start the container:

~~~bash 
git clone https://github.com/pbelmann/docker-monitoring.git &&
cd docker-monitoring &&
sudo docker-compose up
~~~

Each of the applications is now active which can be verified with the browser:

* cadvisor: http://localhost:8080
* influxdb: http://localhost:8083
* grafana: http://localhost:3000

### Configuration

1. Open grafana in your browser: `http://0.0.0.0:3000`.
2. Login with username: `admin` and password `admin`. 
3. Click on the Grafana icon (The Fireball icon upper left corner)
4. Click on **Data Sources**
5. Click on **Add New** (upper panel)
7. Fill in the following information:
   * Name: influxdb
   * Default: yes
   * Type:  InfluxDb 0.8.x
   * Url: http://influxsrv:8086
   * Basic Auth: 
      * Enable: yes
      * User: admin
      * Password: admin
   * Database cadvisor
   * User: root
   * Password: root
8. Click on **Add**
9. Click on **Dashboards**
10. Click on **Home** -> **Import** -> **Browse** and select the file [docker-monitoring.json](https://github.com/pbelmann/docker-monitoring/blob/master/docker-monitoring.json) which you have downloaded with the repository in the Installation step. You should now see four panels.
