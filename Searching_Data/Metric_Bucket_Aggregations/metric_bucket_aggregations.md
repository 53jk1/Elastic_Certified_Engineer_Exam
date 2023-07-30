# 📊 Write and Execute Metric and Bucket Aggregations

In this section, we will learn how to write and execute metric and bucket aggregations in Elasticsearch.

## 📚 Learning Materials

Here are some resources to help you understand this topic:

- [Aggregations | Elasticsearch Reference [8.1] | Elastic](https://www.elastic.co/guide/en/elasticsearch/reference/current/search-aggregations.html)
- [An Introduction to Elasticsearch Aggregations](https://logz.io/blog/elasticsearch-aggregations)

## 🛠️ Exercises

1. Let's assume you have an index `test_index` with documents that have a `price` field. Write a search query that calculates the average `price` for all documents. Here is an example of how you can do this:

```bash
GET /test_index/_search
{
  "size": 0,
  "aggs" : {
    "avg_price" : { "avg" : { "field" : "price" } }
  }
}
```

2. Now, let's do a bucket aggregation. Suppose each document also has a `category` field. Write a search query that calculates the average `price` for each `category`.

```bash
GET /test_index/_search
{
  "size": 0,
  "aggs" : {
    "categories" : {
      "terms" : { "field" : "category.keyword" },
      "aggs" : {
        "avg_price" : { "avg" : { "field" : "price" } }
      }
    }
  }
}
```

Remember to use a tool like cURL, Postman, or Kibana Dev Tools to interact with your Elasticsearch cluster.
