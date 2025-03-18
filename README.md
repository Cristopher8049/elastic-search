# Running Elasticsearch with Docker

This guide provides step-by-step instructions on how to deploy Elasticsearch using Docker.

##What is Elasticsearch?

Elasticsearch is a powerful, open-source search and analytics engine built on top of the Apache Lucene library. It provides a distributed, scalable, and high-performance platform for storing, searching, and analyzing data in real time.

## Prerequisites

- Docker installed on your system

## Deploying Elasticsearch with Docker

### 1. Pull the Elasticsearch Image

```sh
docker pull docker.elastic.co/elasticsearch/elasticsearch:8.17.3
```

### 2. Run Elasticsearch Container

```sh
docker run -d --name elasticsearch \
  -p 9200:9200 -p 9300:9300 \
  -e "discovery.type=single-node" \
docker.elastic.co/elasticsearch/elasticsearch:8.17.3
```

### 3. Verify the Deployment

Run the following command to check if Elasticsearch is running:

```sh
curl -X GET "http://localhost:9200/"
```

You should see a response similar to:

```json
{
  "name" : "instance",
  "cluster_name" : "docker-cluster",
  "version" : {
    "number" : "8.5.0",
    "build_flavor" : "default",
    "build_type" : "docker"
  }
}
```
