# Prometheus / Grafana stack

To use this stack with a application run on your host:

> For example, if your application run in docker, you must find IP address with the following command :

```
$ sudo docker inspect  docker_dev-app_1 | grep IPAddress
            "SecondaryIPAddresses": null,
            "IPAddress": "",
                    "IPAddress": "172.18.0.3",
```

or

```
$ sudo docker inspect  docker_dev-app_1 | grep Gateway
            "IPv6Gateway": "",
                    "Gateway": "172.19.0.1",
                    "IPv6Gateway": "",

```

> With the IP address, you must set good value in the file **prometheus/prometheus.yml** 

replace **172.19.0.1** by the good IP address

```
    - targets: 
      - 172.19.0.1:8080

```


http_server_requests_seconds_max{exception="None",method="GET",status="200",uri="/actuator/prometheus",} 

