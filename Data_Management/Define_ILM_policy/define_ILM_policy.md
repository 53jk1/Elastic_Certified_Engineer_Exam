# 🔄 Define an Index Lifecycle Management Policy for a Time-Series Index

In this section, we will learn how to define an Index Lifecycle Management (ILM) policy for a time-series index in Elasticsearch.

## 📚 Learning Materials

Here are some resources to help you understand this topic:

- [Index Lifecycle Management | Elasticsearch Reference [8.1] | Elastic](https://www.elastic.co/guide/en/elasticsearch/reference/current/index-lifecycle-management.html)
- [Getting started with Index Lifecycle Management | Elasticsearch Reference [8.1] | Elastic](https://www.elastic.co/guide/en/elasticsearch/reference/current/getting-started-index-lifecycle-management.html)

## 🛠️ Exercises

1. Define an ILM policy `test_policy` that rolls over the index after it reaches 50GB or 30 days old, and deletes the index after 1 year. Here is an example of how you can do this:

```bash
PUT _ilm/policy/test_policy
{
  "policy": {
    "phases": {
      "hot": {
        "actions": {
          "rollover": {
            "max_size": "50GB",
            "max_age": "30d"
          }
        }
      },
      "delete": {
        "min_age": "1y",
        "actions": {
          "delete": {}
        }
      }
    }
  }
}
```

2. You can nowy apply this policy to any new index that you create.

Remember to use a tool like cURL, Postman, or Kibana Dev Tools to interact with your Elasticsearch cluster.
