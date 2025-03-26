# docker-opensearch (simple, standalone node)
See https://hub.docker.com/r/opensearchproject/opensearch

# Bring up OpenSearch server

    % docker-compose up -d

# Interacting with OpenSearch REST API

    % docker-opensearch curl -X GET "https://localhost:9200" -ku admin:<PW>
    {
      "name" : "4d82cc619a37",
      "cluster_name" : "docker-cluster",
      "cluster_uuid" : "3j6aZcE7R9Ku-NVdgQKLFw",
      "version" : {
        "distribution" : "opensearch",
        "number" : "2.19.1",
        "build_type" : "tar",
        "build_hash" : "2e4741fb45d1b150aaeeadf66d41445b23ff5982",
        "build_date" : "2025-02-27T01:22:24.665339607Z",
        "build_snapshot" : false,
        "lucene_version" : "9.12.1",
        "minimum_wire_compatibility_version" : "7.10.0",
        "minimum_index_compatibility_version" : "7.0.0"
      },
      "tagline" : "The OpenSearch Project: https://opensearch.org/"
    }
    
    % docker-opensearch curl -X GET "https://localhost:9200/_cat/nodes?v" -ku admin:<PW>
    ip         heap.percent ram.percent cpu load_1m load_5m load_15m node.role node.roles                                        cluster_manager name
    172.23.0.2           14          99   0    2.73    2.40     2.07 dimr      cluster_manager,data,ingest,remote_cluster_client *               4d82cc619a37
    
    % docker-opensearch curl -X GET "https://localhost:9200/_cat/plugins?v" -ku admin:<PW>
    name         component                            version
    4d82cc619a37 opensearch-alerting                  2.19.1.0
    4d82cc619a37 opensearch-anomaly-detection         2.19.1.0
    4d82cc619a37 opensearch-asynchronous-search       2.19.1.0
    4d82cc619a37 opensearch-cross-cluster-replication 2.19.1.0
    4d82cc619a37 opensearch-custom-codecs             2.19.1.0
    4d82cc619a37 opensearch-flow-framework            2.19.1.0
    4d82cc619a37 opensearch-geospatial                2.19.1.0
    4d82cc619a37 opensearch-index-management          2.19.1.0
    4d82cc619a37 opensearch-job-scheduler             2.19.1.0
    4d82cc619a37 opensearch-knn                       2.19.1.0
    4d82cc619a37 opensearch-ltr                       2.19.1.0
    4d82cc619a37 opensearch-ml                        2.19.1.0
    4d82cc619a37 opensearch-neural-search             2.19.1.0
    4d82cc619a37 opensearch-notifications             2.19.1.0
    4d82cc619a37 opensearch-notifications-core        2.19.1.0
    4d82cc619a37 opensearch-observability             2.19.1.0
    4d82cc619a37 opensearch-performance-analyzer      2.19.1.0
    4d82cc619a37 opensearch-reports-scheduler         2.19.1.0
    4d82cc619a37 opensearch-security                  2.19.1.0
    4d82cc619a37 opensearch-security-analytics        2.19.1.0
    4d82cc619a37 opensearch-skills                    2.19.1.0
    4d82cc619a37 opensearch-sql                       2.19.1.0
    4d82cc619a37 opensearch-system-templates          2.19.1.0
    4d82cc619a37 query-insights                       2.19.1.0
    
