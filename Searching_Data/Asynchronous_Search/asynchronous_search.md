# ⏱️ Write an Asynchronous Search

In this section, we will learn how to write an asynchronous search in Elasticsearch.

## 📚 Learning Materials

Here are some resources to help you understand this topic:

- [Asynchronous search | Elasticsearch Reference [8.1] | Elastic](https://www.elastic.co/guide/en/elasticsearch/reference/current/async-search.html)

## 🛠️ Exercises

1. Let's start by executing an asynchronous search that will return the top 100 documents matching a query. We will search for the term "elasticsearch" in the "title" field of the `test_index` index:

```bash
POST /test_index/_async_search?size=100
{
  "query": {
    "match": {
      "title": "elasticsearch"
    }
  }
}
```

This operation will return a response that includes the ID of the search, the search status, and any available results.

2. To get the status and results of the search, you can use the ID of the search like so:

```bash
GET /_async_search/<search_id>
```

Remember to replace `<search_id>` with the actual ID of the search.

Remember to use a tool like cURL, Postman, or Kibana Dev Tools to interact with your Elasticsearch cluster.


