# 💡 Highlight Search Terms in the Response of a Query

In this section, we will learn how to highlight the search terms in the response of a query in Elasticsearch.

## 📚 Learning Materials

Here are some resources to help you understand this topic:

- [Highlighting | Elasticsearch Reference [8.1] | Elastic](https://www.elastic.co/guide/en/elasticsearch/reference/current/highlighting.html)
- [Better search with query time boosting and result highlighting](https://www.elastic.co/blog/better-search-with-query-time-boosting-and-result-highlighting)

## 🛠️ Exercises

1. Let's assume you have an index `test_index` with documents that have a `description` field. Write a search query that searches for the term "elasticsearch" in the `description` field and highlights the search term in the response. Here is an example of how you can do this:

```bash
GET /test_index/_search
{
  "query": {
    "match" : {
      "description" : "elasticsearch"
    }
  },
  "highlight": {
    "fields" : {
      "description" : {}
    }
  }
}
```

Remember to use a tool like cURL, Postman, or Kibana Dev Tools to interact with your Elasticsearch cluster.
