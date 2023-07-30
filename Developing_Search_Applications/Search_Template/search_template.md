# 📝 Define and Use a Search Template

In this section, we will learn how to define and use a search template in Elasticsearch.

## 📚 Learning Materials

Here are some resources to help you understand this topic:

- [Search templates | Elasticsearch Reference [8.1] | Elastic](https://www.elastic.co/guide/en/elasticsearch/reference/current/search-template.html)
- [Elasticsearch Search Template](https://www.tutorialspoint.com/elasticsearch/elasticsearch_search_template.htm)

## 🛠️ Exercises

1. Let's start by creating a search template. In this example, we'll create a simple template that allows us to search for a particular term in a specific field. We'll call this template `search_template_1`:

```bash
POST _scripts/search_template_1
{
  "script": {
    "lang": "mustache",
    "source": {
      "query": { "match" : { "{{fieldName}}" : "{{query}}" } }
    }
  }
}
```

2. Now, let's use the search template we just created. We will search for the term "elasticsearch" in the "description" field of the `test_index` index:

```bash
GET /test_index/_search/template
{
  "id": "search_template_1",
  "params": {
    "fieldName": "description",
    "query": "elasticsearch"
  }
}
```

This should return the documents that contain the term "elasticsearch" in their "description" field.

Remember to use a tool like cURL, Postman, or Kibana Dev Tools to interact with your Elasticsearch cluster.


