# 🛠️ Define and Use a Custom Analyzer

In this section, we will learn how to define and use a custom analyzer in Elasticsearch.

## 📚 Learning Materials

Here are some resources to help you understand this topic:

- [Analysis | Elasticsearch Reference [8.1] | Elastic](https://www.elastic.co/guide/en/elasticsearch/reference/current/analysis.html)
- [Custom Analyzer | Elasticsearch Reference [8.1] | Elastic](https://www.elastic.co/guide/en/elasticsearch/reference/current/analysis-custom-analyzer.html)

## 🛠️ Exercises

1. Let's create a custom analyzer that uses the standard tokenizer, lowercases the terms, and applies the stop and kstem (stemming) filters. You can define this custom analyzer when creating a new index. Here is an example:

```bash
PUT /test_index
{
  "settings": {
    "analysis": {
      "analyzer": {
        "my_custom_analyzer": {
          "tokenizer": "standard",
          "filter": ["lowercase", "stop", "kstem"]
        }
      }
    }
  }
}
```

2. Now, test your custom analyzer using the `_analyze` API:

```bash
GET /test_index/_analyze
{
  "analyzer": "my_custom_analyzer",
  "text": "Running jumped"
}
```

This should return the analyzed tokens for the input text.

Remember to use a tool like cURL, Postman, or Kibana Dev Tools to interact with your Elasticsearch cluster.
