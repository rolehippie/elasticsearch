# elasticsearch

[![Source Code](https://img.shields.io/badge/github-source%20code-blue?logo=github&logoColor=white)](https://github.com/rolehippie/elasticsearch) [![Build Status](https://img.shields.io/drone/build/rolehippie/elasticsearch/master?logo=drone)](https://cloud.drone.io/rolehippie/elasticsearch) [![License: Apache-2.0](https://img.shields.io/github/license/rolehippie/elasticsearch)](https://github.com/rolehippie/elasticsearch/blob/master/LICENSE) 

Ansible role to install and configure a Elasticsearch full-text search engine. 

## Sponsor 

[![Proact Deutschland GmbH](https://proact.eu/wp-content/uploads/2020/03/proact-logo.png)](https://proact.eu) 

Building and improving this Ansible role have been sponsored by my employer **Proact Deutschland GmbH**.

## Table of content

* [Default Variables](#default-variables)
  * [elasticsearch_bootstrap_memory_lock](#elasticsearch_bootstrap_memory_lock)
  * [elasticsearch_cli_version](#elasticsearch_cli_version)
  * [elasticsearch_cluster_name](#elasticsearch_cluster_name)
  * [elasticsearch_default_folders](#elasticsearch_default_folders)
  * [elasticsearch_default_labels](#elasticsearch_default_labels)
  * [elasticsearch_default_publish](#elasticsearch_default_publish)
  * [elasticsearch_default_volumes](#elasticsearch_default_volumes)
  * [elasticsearch_discovery_seed_hosts](#elasticsearch_discovery_seed_hosts)
  * [elasticsearch_exporter_cluster_settings](#elasticsearch_exporter_cluster_settings)
  * [elasticsearch_exporter_default_labels](#elasticsearch_exporter_default_labels)
  * [elasticsearch_exporter_default_publish](#elasticsearch_exporter_default_publish)
  * [elasticsearch_exporter_default_volumes](#elasticsearch_exporter_default_volumes)
  * [elasticsearch_exporter_enabled](#elasticsearch_exporter_enabled)
  * [elasticsearch_exporter_extra_labels](#elasticsearch_exporter_extra_labels)
  * [elasticsearch_exporter_extra_publish](#elasticsearch_exporter_extra_publish)
  * [elasticsearch_exporter_extra_volumes](#elasticsearch_exporter_extra_volumes)
  * [elasticsearch_exporter_image](#elasticsearch_exporter_image)
  * [elasticsearch_exporter_indicies](#elasticsearch_exporter_indicies)
  * [elasticsearch_exporter_indicies_settings](#elasticsearch_exporter_indicies_settings)
  * [elasticsearch_exporter_node](#elasticsearch_exporter_node)
  * [elasticsearch_exporter_shards](#elasticsearch_exporter_shards)
  * [elasticsearch_exporter_snapshots](#elasticsearch_exporter_snapshots)
  * [elasticsearch_exporter_version](#elasticsearch_exporter_version)
  * [elasticsearch_extra_folders](#elasticsearch_extra_folders)
  * [elasticsearch_extra_labels](#elasticsearch_extra_labels)
  * [elasticsearch_extra_publish](#elasticsearch_extra_publish)
  * [elasticsearch_extra_volumes](#elasticsearch_extra_volumes)
  * [elasticsearch_image](#elasticsearch_image)
  * [elasticsearch_initial_heap](#elasticsearch_initial_heap)
  * [elasticsearch_initial_master_nodes](#elasticsearch_initial_master_nodes)
  * [elasticsearch_maximum_heap](#elasticsearch_maximum_heap)
  * [elasticsearch_network](#elasticsearch_network)
  * [elasticsearch_node_name](#elasticsearch_node_name)
  * [elasticsearch_single_node](#elasticsearch_single_node)
  * [elasticsearch_version](#elasticsearch_version)
* [Dependencies](#dependencies)
* [License](#license)
* [Author](#author)

---

## Default Variables

### elasticsearch_bootstrap_memory_lock

Enable memory lock within bootstrap

#### Default value

```YAML
elasticsearch_bootstrap_memory_lock: false
```

### elasticsearch_cli_version

Version of esctl installed via pip

#### Default value

```YAML
elasticsearch_cli_version: latest
```

### elasticsearch_cluster_name

Name of the cluster to create

#### Default value

```YAML
elasticsearch_cluster_name:
```

### elasticsearch_default_folders

List of default folders to create

#### Default value

```YAML
elasticsearch_default_folders:
  - /var/lib/elasticsearch
```

### elasticsearch_default_labels

List of default labels to assign to elasticsearch

#### Default value

```YAML
elasticsearch_default_labels: []
```

### elasticsearch_default_publish

List of default port publishing for elasticsearch exporter

#### Default value

```YAML
elasticsearch_default_publish:
  - 9200:9200
```

### elasticsearch_default_volumes

List of default volumes to mount to elasticsearch

#### Default value

```YAML
elasticsearch_default_volumes:
  - /var/lib/elasticsearch:/usr/share/elasticsearch/data
```

### elasticsearch_discovery_seed_hosts

List of discovery seed hosts

#### Default value

```YAML
elasticsearch_discovery_seed_hosts: []
```

#### Example usage

```YAML
elasticsearch_discovery_seed_hosts:
  - host01
  - host02
  - host03
  - host04
  - host05
```

### elasticsearch_exporter_cluster_settings

Export stats for cluster settings

#### Default value

```YAML
elasticsearch_exporter_cluster_settings: true
```

### elasticsearch_exporter_default_labels

List of default labels to assign to elasticsearch exporter

#### Default value

```YAML
elasticsearch_exporter_default_labels: []
```

### elasticsearch_exporter_default_publish

#### Default value

```YAML
elasticsearch_exporter_default_publish:
  - 9114:9114
```

### elasticsearch_exporter_default_volumes

List of default volumes to mount to elasticsearch exporter

#### Default value

```YAML
elasticsearch_exporter_default_volumes: []
```

#### Example usage

```YAML
elasticsearch_exporter_default_volumes:
  - /path/to/host/folder1:/path/within/container1
  - /path/to/host/folder2:/path/within/container2
  - /path/to/host/folder3:/path/within/container3
```

### elasticsearch_exporter_enabled

Enable the elasticsearch exporter

#### Default value

```YAML
elasticsearch_exporter_enabled: true
```

### elasticsearch_exporter_extra_labels

List of extra labels to assign to elasticsearch exporter

#### Default value

```YAML
elasticsearch_exporter_extra_labels: []
```

### elasticsearch_exporter_extra_publish

List of extra port publishing for elasticsearch exporter

#### Default value

```YAML
elasticsearch_exporter_extra_publish: []
```

#### Example usage

```YAML
elasticsearch_exporter_extra_publish:
  - 8080:8080
  - 127.0.0.1:9000:9000
```

### elasticsearch_exporter_extra_volumes

List of extra volumes to mount to elasticsearch exporter

#### Default value

```YAML
elasticsearch_exporter_extra_volumes: []
```

#### Example usage

```YAML
elasticsearch_exporter_extra_volumes:
  - /path/to/host/folder1:/path/within/container1
  - /path/to/host/folder2:/path/within/container2
  - /path/to/host/folder3:/path/within/container3
```

### elasticsearch_exporter_image

Docker image for elasticsearch exporter

#### Default value

```YAML
elasticsearch_exporter_image: justwatch/elasticsearch_exporter:{{ elasticsearch_exporter_version
  }}
```

### elasticsearch_exporter_indicies

Export stats for indices in the cluster

#### Default value

```YAML
elasticsearch_exporter_indicies: true
```

### elasticsearch_exporter_indicies_settings

Export stats for settings of all indices of the cluster

#### Default value

```YAML
elasticsearch_exporter_indicies_settings: true
```

### elasticsearch_exporter_node

Name of the node to export, all for every node

#### Default value

```YAML
elasticsearch_exporter_node: all
```

### elasticsearch_exporter_shards

Export stats for shards in the cluster

#### Default value

```YAML
elasticsearch_exporter_shards: true
```

### elasticsearch_exporter_snapshots

Export stats for the cluster snapshots

#### Default value

```YAML
elasticsearch_exporter_snapshots: true
```

### elasticsearch_exporter_version

Version of the elasticsearch exporter image

#### Default value

```YAML
elasticsearch_exporter_version: 1.1.0
```

### elasticsearch_extra_folders

List of extra folders to create

#### Default value

```YAML
elasticsearch_extra_folders: []
```

#### Example usage

```YAML
elasticsearch_extra_folders:
  - /path/to/host/folder1
  - /path/to/host/folder2
  - /path/to/host/folder3
```

### elasticsearch_extra_labels

List of extra labels to assign to elasticsearch

#### Default value

```YAML
elasticsearch_extra_labels: []
```

### elasticsearch_extra_publish

List of extra port publishing for elasticsearch

#### Default value

```YAML
elasticsearch_extra_publish: []
```

#### Example usage

```YAML
elasticsearch_extra_publish:
  - 127.0.0.1:9000:9000
```

### elasticsearch_extra_volumes

List of extra volumes to mount to elasticsearch

#### Default value

```YAML
elasticsearch_extra_volumes: []
```

#### Example usage

```YAML
elasticsearch_extra_volumes:
  - /path/to/host/folder1:/path/within/container1
  - /path/to/host/folder2:/path/within/container2
  - /path/to/host/folder3:/path/within/container3
```

### elasticsearch_image

Docker image for elasticsearch

#### Default value

```YAML
elasticsearch_image: docker.elastic.co/elasticsearch/elasticsearch-oss:{{ elasticsearch_version
  }}
```

### elasticsearch_initial_heap

Initial heap size

#### Default value

```YAML
elasticsearch_initial_heap: 256m
```

### elasticsearch_initial_master_nodes

List of initial master nodes

#### Default value

```YAML
elasticsearch_initial_master_nodes: []
```

#### Example usage

```YAML
elasticsearch_initial_master_nodes:
  - node01
  - node02
  - node03
```

### elasticsearch_maximum_heap

Maximum heap size

#### Default value

```YAML
elasticsearch_maximum_heap: 256m
```

### elasticsearch_network

Optionally assign this network to container

#### Default value

```YAML
elasticsearch_network:
```

### elasticsearch_node_name

Name of this node within cluster

#### Default value

```YAML
elasticsearch_node_name:
```

### elasticsearch_single_node

Launch elasticsearch as single node

#### Default value

```YAML
elasticsearch_single_node: false
```

### elasticsearch_version

Version of the elasticsearch image

#### Default value

```YAML
elasticsearch_version: 7.9.3
```

## Dependencies

* [rolehippie.docker](https://github.com/rolehippie/docker)

## License

Apache-2.0

## Author

[Thomas Boerger](https://github.com/tboerger)
