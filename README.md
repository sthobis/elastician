# Elastician

A set of tools to easily develop and manage Elasticsearch and the Elastic Stack

## Build or get from Docker Hub

Get from Docker Hub:

```bash
docker pull bigdataboutique/elastician
```

Build locally:

```bash
docker build .
```

## Commands

### Dump an index to a file

```bash
docker run  -v `pwd`:/data --rm bigdataboutique/elastician dump myindex --hosts http://10.63.246.27:9200
``` 

### Upload file and ingest it into an index 

```bash
docker run  -v `pwd`:/data --rm bigdataboutique/elastician ingest myindex_dump.jsonl.gz myindex --hosts http://10.63.246.27:9200
```

### Copy index between clusters

```bash
docker run  --rm bigdataboutique/elastician copy source_index_name http://target-cluster:9200 --hosts http://10.63.246.27:9200
```