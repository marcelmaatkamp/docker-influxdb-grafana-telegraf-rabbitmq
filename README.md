# docker-influxdb-grafana-telegraf-rabbitmq

Start Influxdb Grafana Telegraf and RabbitMQ in Docker

Starts graphing messages sent to RabbitMQ exchange 'amq.topic' with routing key 'sensor/+/#' (which can be changed in conf/telegraf/telegraf.conf). Data is stored in InfluxDB in the database 'telegraf' and table 'mqtt_consumer'. 

An example query to display the measurements in a Grafana Dashboard looks like this:

```
SELECT "payload_value" FROM "mqtt_consumer" WHERE "topic" = 'sensor/0022/1' AND $timeFilter
```

# Start

```
docker-compose up
```

# Add an Influxdb datasource

![Screen%20Shot%202017-04-10%20at%2014.28.34.png](Screen%20Shot%202017-04-10%20at%2014.28.34.png)

# Screenshot of measurements

![Screen%20Shot%202017-04-10%20at%2014.43.41.png](Screen%20Shot%202017-04-10%20at%2014.43.41.png)

