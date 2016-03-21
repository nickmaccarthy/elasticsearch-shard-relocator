# Elasticsearch Shard Relocator

# What?

A script to relocate UNASSINGED shards in an ES Cluster

# Why?

Sometimes shards become unassigned due to issues with the cluster.  ES usually does a good job of re-assiging them, but sometimes it gets stuck.  This script aim to give it a little kick in the butt and get your cluster green again.

# How do I use it?
1. In the directory you extracted or cloned this to:
```virtualenv env && source env/bin/activate```
2. Now install the requirements
```pip install -r requirements.txt```
3. Move es_hosts.yml.example to es_hosts.yml
```mv es_hosts.yml.example es_hosts.yml```
4. Edit es_hosts.yml and fill in the correct info
5. Run it
```python shard-relocate.py```
6. Once cluster status is green, grab a beer
7. Profit


# Requirements
1. Python 2.7 ( might work with 3, but havent tested )
2. Virtualenv
3. Pip
4. An Elasticsearch cluster

# New Features
1.) Added the ability to specify '_all_data_nodes' in hosts.yml.  This will run nodeclient.info() and determine all 'data nodes' in your cluster that will be eligable for shard reassingment
