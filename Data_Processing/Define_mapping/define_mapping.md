# 🗺️ Define a Mapping that Satisfies a Given Set of Requirements

In this section, we will learn how to define a mapping in Elasticsearch that satisfies a given set of requirements.

## 📚 Learning Materials

Here are some resources to help you understand this topic:

- [Mapping | Elasticsearch Guide [8.1] | Elastic](https://www.elastic.co/guide/en/elasticsearch/reference/current/mapping.html)
- [Deep Dive into Elasticsearch Mapping](https://medium.com/@Bose_Anurag/deep-dive-into-elasticsearch-mapping-d7f76b8ac814)

## 🛠️ Exercises

1. Define a mapping for an index `test_mapping` that has a `title` field of type `text`, a `date` field of type `date`, and a `views` field of type `integer`. Here is an example of how you can do this:

```bash
PUT /test_mapping
{
  "mappings": {
    "properties": {
      "title": { "type": "text" },
      "date": { "type": "date" },
      "views": { "type": "integer" }
    }
  }
}
```

2. Now, you can add documents to the `test-mapping` index and they will follow the defined mapping.

Remember to use a tool like cURL, Postman, or Kibana Dev Tools to interact with your Elasticsearch cluster.
