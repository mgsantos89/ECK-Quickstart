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


- 5 - Deployment do Filebeat

    ```
    kubectl apply -f filebeat.yaml
    ```

- 6 - Deployment do HeartBeat

    ```
    kubectl apply -f heartbeat.yaml
    ```


# Removendo ECK Stack

1 - Remover Recursos ECK em todos os Namespaces

    ```
    kubectl get namespaces --no-headers -o custom-columns=:metadata.name \
  | xargs -n1 kubectl delete elastic --all -n
    ```


2 - Remover Operator e CRDS instalados no Cluster

    ```
        kubectl delete -f https://download.elastic.co/downloads/eck/2.11.1/operator.yaml
        kubectl delete -f https://download.elastic.co/downloads/eck/2.11.1/crds.yaml
    ```
