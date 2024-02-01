# ECK-Quickstart
Repositorio Quickstart do Elastic Stack on Kubernetes


# Stack
    1 Node Funcional ElasticSearch
    1 Kibana Funcional
    1 Filebeat Coletando as Logs do meu cluster k8s.
    1 HeartBeat para Uptime

# Passos

- 1 - Criação das Resources Definitions

    ```
    kubectl create -f https://download.elastic.co/downloads/eck/2.11.1/crds.yaml

    ```

- 2 - Instalação do Operator e dos regras RBAC

    ```
    kubectl apply -f https://download.elastic.co/downloads/eck/2.11.1/operator.yaml

    ```

- 3 - Deployment do Elasticsearch

    ```
    kubectl apply -f elasticsearch-cluster.yaml
    ```

- 4 - Deployment do Kibana

    ```
    kubectl apply -f kibana.yaml
    ```


- 4 - Deployment do Filebeat

    ```
    kubectl apply -f filebeat.yaml
    ```

- 5 - Deployment do HeartBeat

    ```
    kubectl apply -f heartbeat.yaml
    ```
