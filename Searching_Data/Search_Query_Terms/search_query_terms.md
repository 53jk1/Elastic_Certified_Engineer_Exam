# 🔍 Write and Execute a Search Query for Terms and/or Phrases

In this section, we will learn how to write and execute a search query for terms and/or phrases in one or more fields of an index in Elasticsearch.

## 📚 Learning Materials

Here are some resources to help you understand this topic:

- [Full text queries | Elasticsearch Reference [8.1] | Elastic](https://www.elastic.co/guide/en/elasticsearch/reference/current/full-text-queries.html)
- [Match Query | Elasticsearch Reference [8.1] | Elastic](https://www.elastic.co/guide/en/elasticsearch/reference/current/query-dsl-match-query.html)

## 🛠️ Exercises

1. Let's start by searching for the term "elasticsearch" in the "title" field of the `test_index` index. Here is how you can do this:

```bash
GET /test_index/_search
{
  "query": {
    "match": {
      "title": "elasticsearch"
    }
  }
}
```

2. Now let's search for the phrase "open source search engine" in the "description" field of the `test_index` index:

```bash
GET /test_index/_search
{
  "query": {
    "match_phrase": {
      "description": "open source search engine"
    }
  }
}
```

This should return the documents that contain the exact phrase "open source search engine" in their "description" field.

Remember to use a tool like cURL, Postman, or Kibana Dev Tools to interact with your Elasticsearch cluster.
