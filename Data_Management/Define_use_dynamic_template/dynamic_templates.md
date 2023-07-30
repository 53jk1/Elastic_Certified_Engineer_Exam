# 🎭 Define and Use a Dynamic Template

In this section, we'll delve into how to define and use dynamic templates in Elasticsearch that satisfies a set of requirements.

## 📚 Learning Materials

Here are some resources to help you understand dynamic templates:

- [Dynamic Templates | Elasticsearch Reference [8.1] | Elastic](https://www.elastic.co/guide/en/elasticsearch/reference/current/dynamic-templates.html)
- [Elasticsearch dynamic templates for beginners](https://dev.to/codingblocks/elastic-search-dynamic-templates-for-beginners-58f8)

## 🛠️ Exercises

1. Define a dynamic template that will apply to any new string field in an index. The string fields should be stored as keyword type instead of text. Here is an example of how you can do this:

```bash
PUT _template/template_1
{
  "index_patterns" : ["test-*"],
  "mappings" : {
    "dynamic_templates" : [
      {
        "strings_as_keyword" : {
          "match_mapping_type" : "string",
          "mapping" : {
            "type" : "keyword"
          }
        }
      }
    ]
  }
}
```

2. Now create a new index `test-dynamic` and add a document to it with a new string field. Verify that the field is stored as a keyword using the `GET test-dynamic/_mapping` command.
Remember to use a tool like cURL, Postman, or Kibana Dev Tools to interact with your Elasticsearch cluster.