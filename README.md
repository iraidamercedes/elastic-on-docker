# Elastic and Kibana 7.8.1 Dockerized :whale:.

A docker-composed file to set up a Elasticsearch engine and kibana visualizator. It only has a node.

## Requirements.

Elastictsearch demads a minimum of memory size to run it. Docker set by default 2 GB of memory for a container. To increase this value you can folowing these steps: 

1. Go to desktop dashboard.
2. Open *Settings*.
3. Open *Resources* tab.
4. Click on *Advance* option and drag to get the value in *Memory* parameter.

![Docker](https://docs.docker.com/docker-for-windows/images/settings-resources.png)

If you're in windows and you don't have the advance tab in resources menu, you can open a powershell with admin privileges to increase the VM mapping value (default is 65530):

```
wsl -d docker-desktop sysctl -w vm.max_map_count=262144
```
Check the value modified:
```
wsl -d docker-desktop cat /proc/sys/vm/max_map_count
```
Response must be 262144.

## Instructions to run it.

Open and run the docker-compose with the following command:

```
docker-compose up
```
Open ```localhost:9200``` and you have to get he following output:

```
{
  "name" : "es01",
  "cluster_name" : "my-elastic-cluster",
  "cluster_uuid" : "7y29AvomRsaj4T6uGJHB4g",
  "version" : {
    "number" : "7.8.1",
    "build_flavor" : "default",
    "build_type" : "docker",
    "build_hash" : "b5ca9c58fb664ca8bf9e4057fc229b3396bf3a89",
    "build_date" : "2020-07-21T16:40:44.668009Z",
    "build_snapshot" : false,
    "lucene_version" : "8.5.1",
    "minimum_wire_compatibility_version" : "6.8.0",
    "minimum_index_compatibility_version" : "6.0.0-beta1"
  },
  "tagline" : "You Know, for Search"
}
```

To access Kibana dashboard go to localhost:5601 and configure visualization.