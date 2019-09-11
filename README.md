# highcharts-export-docker

This repo contains what is required to build the docker image for the highcharts node.js export server: 

https://github.com/highcharts/node-export-server


## Build

```
docker build -t highcharts-export-node . 
```
#### Check docker images

```
docker images 
```

## Run

```
docker run -d --name highcharts -p 7801:8080 highcharts-export-node
```
The above command will expose the service on port 7801. This can be changed if required.


#### Check running containers

```
docker ps -a
```

## Test

Once the server is running here is an example curl command to render a chart:
```
curl -H "Content-Type: application/json" -X POST -d '{"infile":{"title": {"text": "Steep Chart"}, "xAxis": {"categories": ["Jan", "Feb", "Mar"]}, "series": [{"data": [29.9, 71.5, 106.4]}]}}' 127.0.0.1:8889 -o testchart.png
```

#### Stop 

```
docker stop highcharts
```
