# 🎯 Define and Use an Index Template

In this section, we will explore how to define and use an index template in Elasticsearch for a given pattern that satisfies a set of requirements.

## 📘 Learning Materials

Here are some resources to help you understand index templates:

- [Index templates | Elasticsearch Guide [8.1] | Elastic](https://www.elastic.co/guide/en/elasticsearch/reference/current/index-templates.html)
- [Elasticsearch Index Templates: The What, When, How and Why](https://logz.io/blog/elasticsearch-index-templates/)

## 🔧 Exercises

1. Define an index template that will apply to any index starting with `test-` and set the number of shards to 1 and the number of replicas to 2. Here is an example of how you can do this:

```bash
PUT _index_template/test_template
{
  "index_patterns": ["test-*"],
  "template": {
    "settings": {
      "number_of_shards": 1,
      "number_of_replicas": 2
    }
  }
}
```

2. Now create an index `test-index1` and check its settings. It should automatically have the settings defined in the `test-template`.
You can perform these exercises using any tool that allows you to make HTTP requests to your Elasticsearch cluster, such as cURL, Postman, or Kibana Dev Tools.
