# 🔍 Write and Execute a Search Query for Terms and/or Phrases

In this section, we will learn how to write and execute a search query for terms and/or phrases in one or more fields of an index in Elasticsearch.

## 📚 Learning Materials

Here are some resources to help you understand this topic:

- [Full Text Queries | Elasticsearch Guide [8.1] | Elastic](https://www.elastic.co/guide/en/elasticsearch/reference/current/full-text-queries.html) bn                
- [Elasticsearch: The Definitive Guide - Searching—The Basic Tools](https://www.elastic.co/guide/en/elasticsearch/guide/current/search-in-depth.html)

## 🛠️ Exercises

1. Let's assume you have an index `test_index` with documents that have a `title` and `description` field. Write a search query that searches for the term "elasticsearch" in both the `title` and `description` fields. Here is an example of how you can do this:

```bash
GET /test_index/_search
{
  "query": {
    "multi_match" : {
      "query": "elasticsearch",
      "fields": ["title", "description"]
    }
  }
}
```

2. Now write a search query that searched for the phrase "Elastic Certified Engineer" in the `title` field:

```bash
GET /test_index/_search
{
  "query": {
    "match_phrase" : {
      "title" : "Elastic Certified Engineer"
    }
  }
}

```

You can perform these exercises using any tool that allows you to make HTTP requests to your Elasticsearch cluster, such as cURL, Postman, or Kibana Dev Tools.

