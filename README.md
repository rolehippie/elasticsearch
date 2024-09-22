# elasticsearch

[![Source Code](https://img.shields.io/badge/github-source%20code-blue?logo=github&logoColor=white)](https://github.com/rolehippie/elasticsearch)
[![General Workflow](https://github.com/rolehippie/elasticsearch/actions/workflows/general.yml/badge.svg)](https://github.com/rolehippie/elasticsearch/actions/workflows/general.yml)
[![Readme Workflow](https://github.com/rolehippie/elasticsearch/actions/workflows/docs.yml/badge.svg)](https://github.com/rolehippie/elasticsearch/actions/workflows/docs.yml)
[![Galaxy Workflow](https://github.com/rolehippie/elasticsearch/actions/workflows/galaxy.yml/badge.svg)](https://github.com/rolehippie/elasticsearch/actions/workflows/galaxy.yml)
[![License: Apache-2.0](https://img.shields.io/github/license/rolehippie/elasticsearch)](https://github.com/rolehippie/elasticsearch/blob/master/LICENSE)
[![Ansible Role](https://img.shields.io/badge/role-rolehippie.elasticsearch-blue)](https://galaxy.ansible.com/rolehippie/elasticsearch)

Ansible role to install and configure a Elasticsearch full-text search engine.

## Sponsor

Building and improving this Ansible role have been sponsored by my current and previous employers like **[Cloudpunks GmbH](https://cloudpunks.de)** and **[Proact Deutschland GmbH](https://www.proact.eu)**.

## Table of content

- [Requirements](#requirements)
- [Default Variables](#default-variables)
  - [elasticsearch_action_destructive_requires_name](#elasticsearch_action_destructive_requires_name)
  - [elasticsearch_bootstrap_memory_lock](#elasticsearch_bootstrap_memory_lock)
  - [elasticsearch_cluster_initial_master_nodes](#elasticsearch_cluster_initial_master_nodes)
  - [elasticsearch_cluster_name](#elasticsearch_cluster_name)
  - [elasticsearch_discovery_seed_hosts](#elasticsearch_discovery_seed_hosts)
  - [elasticsearch_discovery_zen_minimum_master_nodes](#elasticsearch_discovery_zen_minimum_master_nodes)
  - [elasticsearch_discovery_zen_ping_unicast_hosts](#elasticsearch_discovery_zen_ping_unicast_hosts)
  - [elasticsearch_exporter_cluster_settings](#elasticsearch_exporter_cluster_settings)
  - [elasticsearch_exporter_connection](#elasticsearch_exporter_connection)
  - [elasticsearch_exporter_download](#elasticsearch_exporter_download)
  - [elasticsearch_exporter_enabled](#elasticsearch_exporter_enabled)
  - [elasticsearch_exporter_indicies](#elasticsearch_exporter_indicies)
  - [elasticsearch_exporter_indicies_settings](#elasticsearch_exporter_indicies_settings)
  - [elasticsearch_exporter_node](#elasticsearch_exporter_node)
  - [elasticsearch_exporter_shards](#elasticsearch_exporter_shards)
  - [elasticsearch_exporter_snapshots](#elasticsearch_exporter_snapshots)
  - [elasticsearch_exporter_version](#elasticsearch_exporter_version)
  - [elasticsearch_gateway_recover_after_nodes](#elasticsearch_gateway_recover_after_nodes)
  - [elasticsearch_group](#elasticsearch_group)
  - [elasticsearch_http_compression](#elasticsearch_http_compression)
  - [elasticsearch_http_cors_allow_origin](#elasticsearch_http_cors_allow_origin)
  - [elasticsearch_http_cors_enabled](#elasticsearch_http_cors_enabled)
  - [elasticsearch_http_port](#elasticsearch_http_port)
  - [elasticsearch_indicies_query_bool_max_clause_count](#elasticsearch_indicies_query_bool_max_clause_count)
  - [elasticsearch_initial_heap_space](#elasticsearch_initial_heap_space)
  - [elasticsearch_java_home](#elasticsearch_java_home)
  - [elasticsearch_keyring](#elasticsearch_keyring)
  - [elasticsearch_logs_path](#elasticsearch_logs_path)
  - [elasticsearch_major_version](#elasticsearch_major_version)
  - [elasticsearch_maximum_heap_space](#elasticsearch_maximum_heap_space)
  - [elasticsearch_network_host](#elasticsearch_network_host)
  - [elasticsearch_network_publish_host](#elasticsearch_network_publish_host)
  - [elasticsearch_node_data](#elasticsearch_node_data)
  - [elasticsearch_node_ingest](#elasticsearch_node_ingest)
  - [elasticsearch_node_master](#elasticsearch_node_master)
  - [elasticsearch_node_name](#elasticsearch_node_name)
  - [elasticsearch_openjdk_version](#elasticsearch_openjdk_version)
  - [elasticsearch_plugins_extra](#elasticsearch_plugins_extra)
  - [elasticsearch_plugins_general](#elasticsearch_plugins_general)
  - [elasticsearch_restart_on_upgrade](#elasticsearch_restart_on_upgrade)
  - [elasticsearch_search_max_buckets](#elasticsearch_search_max_buckets)
  - [elasticsearch_server_version](#elasticsearch_server_version)
  - [elasticsearch_startup_sleep_time](#elasticsearch_startup_sleep_time)
  - [elasticsearch_storage_path](#elasticsearch_storage_path)
  - [elasticsearch_user](#elasticsearch_user)
  - [elasticsearch_xpack_security_enabled](#elasticsearch_xpack_security_enabled)
- [Discovered Tags](#discovered-tags)
- [Dependencies](#dependencies)
- [License](#license)
- [Author](#author)

---

## Requirements

- Minimum Ansible version: `2.10`

## Default Variables

### elasticsearch_action_destructive_requires_name

Require explicit names when deleting indices

#### Default value

```YAML
elasticsearch_action_destructive_requires_name: false
```

### elasticsearch_bootstrap_memory_lock

Lock the memory on startup

#### Default value

```YAML
elasticsearch_bootstrap_memory_lock: false
```

### elasticsearch_cluster_initial_master_nodes

List of initial master nodes, only for Elasticsearch >= 7.0

#### Default value

```YAML
elasticsearch_cluster_initial_master_nodes: []
```

### elasticsearch_cluster_name

Name of the cluster

#### Default value

```YAML
elasticsearch_cluster_name:
```

### elasticsearch_discovery_seed_hosts

#### Default value

```YAML
elasticsearch_discovery_seed_hosts: []
```

### elasticsearch_discovery_zen_minimum_master_nodes

Minimum master nodes, only for Elasticsearch < 7.0

#### Default value

```YAML
elasticsearch_discovery_zen_minimum_master_nodes: 1
```

### elasticsearch_discovery_zen_ping_unicast_hosts

List of discovery seed hosts, only for Elasticsearch >= 7.0

#### Default value

```YAML
elasticsearch_discovery_zen_ping_unicast_hosts: []
```

### elasticsearch_exporter_cluster_settings

Export stats for cluster settings

#### Default value

```YAML
elasticsearch_exporter_cluster_settings: true
```

### elasticsearch_exporter_connection

Connection URI to access the Elasticsearch

#### Default value

```YAML
elasticsearch_exporter_connection: http://localhost:9200
```

### elasticsearch_exporter_download

URL to the archive of the release to install

#### Default value

```YAML
elasticsearch_exporter_download: 
  https://github.com/prometheus-community/elasticsearch_exporter/releases/download/v{{
  elasticsearch_exporter_version }}/elasticsearch_exporter-{{ elasticsearch_exporter_version
  }}.linux-amd64.tar.gz
```

### elasticsearch_exporter_enabled

Enable the elasticsearch exporter

#### Default value

```YAML
elasticsearch_exporter_enabled: true
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

Version of the release to install

#### Default value

```YAML
elasticsearch_exporter_version: 1.8.0
```

### elasticsearch_gateway_recover_after_nodes

Block initial recovery after a full cluster restart until N nodes are started

#### Default value

```YAML
elasticsearch_gateway_recover_after_nodes: 1
```

### elasticsearch_group

Name of the group owning Elasticsearch

#### Default value

```YAML
elasticsearch_group: elasticsearch
```

### elasticsearch_http_compression

Enable compression for HTTP

#### Default value

```YAML
elasticsearch_http_compression: true
```

### elasticsearch_http_cors_allow_origin

Define CORS allow origin for HTTP

#### Default value

```YAML
elasticsearch_http_cors_allow_origin:
```

### elasticsearch_http_cors_enabled

Enable CORS for HTTP

#### Default value

```YAML
elasticsearch_http_cors_enabled: false
```

### elasticsearch_http_port

Define the port for the HTTP interface

#### Default value

```YAML
elasticsearch_http_port: 9200
```

### elasticsearch_indicies_query_bool_max_clause_count

#### Default value

```YAML
elasticsearch_indicies_query_bool_max_clause_count:
```

### elasticsearch_initial_heap_space

Represents the initial size of total heap space

#### Default value

```YAML
elasticsearch_initial_heap_space: 1g
```

### elasticsearch_java_home

#### Default value

```YAML
elasticsearch_java_home: /usr/lib/jvm/java-{{ elasticsearch_openjdk_version }}-openjdk-amd64
```

### elasticsearch_keyring

Path for the repository keyring

#### Default value

```YAML
elasticsearch_keyring: /usr/share/keyrings/elastic-archive-keyring.gpg
```

### elasticsearch_logs_path

Path to the logs directory

#### Default value

```YAML
elasticsearch_logs_path: /var/log/elasticsearch
```

### elasticsearch_major_version

Major version built via server version variable

#### Default value

```YAML
elasticsearch_major_version: "{{ elasticsearch_server_version.split('.')[0] }}"
```

### elasticsearch_maximum_heap_space

Represents the maximum size of total heap space

#### Default value

```YAML
elasticsearch_maximum_heap_space: 1g
```

### elasticsearch_network_host

#### Default value

```YAML
elasticsearch_network_host: 0.0.0.0
```

### elasticsearch_network_publish_host

#### Default value

```YAML
elasticsearch_network_publish_host:
```

### elasticsearch_node_data

Let this node work as a data node

#### Default value

```YAML
elasticsearch_node_data: true
```

### elasticsearch_node_ingest

Publish this binding to cluster members

#### Default value

```YAML
elasticsearch_node_ingest: true
```

### elasticsearch_node_master

Let this node work as a master node

#### Default value

```YAML
elasticsearch_node_master: true
```

### elasticsearch_node_name

Name of the node

#### Default value

```YAML
elasticsearch_node_name: '{{ ansible_hostname }}'
```

### elasticsearch_openjdk_version

Version of OpenJDK to install as part of Elasticsearch

#### Default value

```YAML
elasticsearch_openjdk_version: 11
```

### elasticsearch_plugins_extra

List of extra plugins to install

#### Default value

```YAML
elasticsearch_plugins_extra: []
```

#### Example usage

```YAML
elasticsearch_plugins_extra:
  - plugin1
  - plugin2
  - name: plugin3
    state: absent
```

### elasticsearch_plugins_general

List of general plugins to install

#### Default value

```YAML
elasticsearch_plugins_general: []
```

#### Example usage

```YAML
elasticsearch_plugins_general:
  - plugin1
  - plugin2
  - name: plugin3
    state: absent
```

### elasticsearch_restart_on_upgrade

#### Default value

```YAML
elasticsearch_restart_on_upgrade: true
```

### elasticsearch_search_max_buckets

#### Default value

```YAML
elasticsearch_search_max_buckets:
```

### elasticsearch_server_version

Version of Elasticsearch that gets installed

#### Default value

```YAML
elasticsearch_server_version: '6.8'
```

### elasticsearch_startup_sleep_time

#### Default value

```YAML
elasticsearch_startup_sleep_time: 5
```

### elasticsearch_storage_path

Path to the storage directory

#### Default value

```YAML
elasticsearch_storage_path: /var/lib/elasticsearch
```

### elasticsearch_user

Number of seconds to wait before checking if Elasticsearch started successfully

#### Default value

```YAML
elasticsearch_user: elasticsearch
```

### elasticsearch_xpack_security_enabled

Maximum number of aggregation buckets allowed in a single response

#### Default value

```YAML
elasticsearch_xpack_security_enabled: false
```

## Discovered Tags

**_elasticsearch_**

**_elasticsearch-exporter_**

**_molecule-idempotence-notest_**


## Dependencies

- None

## License

Apache-2.0

## Author

[Thomas Boerger](https://github.com/tboerger)
