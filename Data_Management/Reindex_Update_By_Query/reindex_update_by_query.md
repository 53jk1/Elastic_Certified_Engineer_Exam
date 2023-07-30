# 🔄 Use the Reindex API and Update By Query API

In this section, we will learn how to use the Reindex API and Update By Query API to reindex and/or update documents in Elasticsearch.

## 📚 Learning Materials

Here are some resources to help you understand this topic:

- [Reindex API | Elasticsearch Reference [8.1] | Elastic](https://www.elastic.co/guide/en/elasticsearch/reference/current/docs-reindex.html)
- [Update by query API | Elasticsearch Reference [8.1] | Elastic](https://www.elastic.co/guide/en/elasticsearch/reference/current/docs-update-by-query.html)

## 🛠️ Exercises

1. Let's start with the Reindex API. Suppose you want to reindex documents from `old_index` to `new_index`. Here is how you can do this:

```bash
POST /_reindex
{
  "source": {
    "index": "old_index"
  },
  "dest": {
    "index": "new_index"
  }
}
```

2. Now, let's use the Update By Query API. Assume you want to update all documents in the `test_index` index that have the `price` field set to 100, and you want to change this `price` to 150. Here's how you can achieve this:

```bash
POST /test_index/_update_by_query
{
  "script": {
    "source": "ctx._source.price = 150",
    "lang": "painless"
  },
  "query": {
    "term": {
      "price": 100
    }
  }
}
```

Remember to use a tool like cURL, Postman, or Kibana Dev Tools to interact with your Elasticsearch cluster.


