# 🚑 Diagnose Shard Issues and Repair a Cluster's Health

In this section, we will learn how to diagnose shard issues and repair a cluster's health in Elasticsearch.

## 📚 Learning Materials

Here are some resources to help you understand this topic:

- [Cluster Health | Elasticsearch Reference [8.1] | Elastic](https://www.elastic.co/guide/en/elasticsearch/reference/current/cluster-health.html)
- [Red Elasticsearch Cluster? Here's How to Fix It](https://logz.io/blog/red-elasticsearch-cluster-heres-fix/)

## 🛠️ Exercises

1. Use the Cluster Health API to check the status of your cluster. The cluster health status is: green, yellow or red. Here is an example of how you can do this:

```bash
GET /_cluster/health
```

2. If the status is not green, use Cluster Allocation Explain API to diagnose shard issues:

```bash
GET /_cluster/allocation/explain
```

3. Depending on the issues diagnosed, take the necessary steps to repair your cluster's health. This might involve actions like increasing disk space, fixing network issues, or adjusting the number of replicas.

Remember to use a tool like cURL, Postman, or Kibana Dev Tools to interact with your Elasticsearch cluster.
