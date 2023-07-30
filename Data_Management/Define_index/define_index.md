# 🔍 Define an Index

In this section, we will learn how to define an index in Elasticsearch that satisfies a given set of requirements.

## 📚 Learning Materials

Here are some resources to help you understand this topic:

- [Elasticsearch: The Definitive Guide - Indexing Employee Documents](https://www.elastic.co/guide/en/elasticsearch/guide/current/index-doc.html)
- [Elasticsearch from the Bottom Up - What is an Index?](https://www.elastic.co/blog/found-elasticsearch-from-the-bottom-up)

## 🛠️ Exercises

1. Create an index with the following requirements:
   - Name: `test_index`
   - Settings: 1 primary shard, no replicas
   - Mappings: `title` (text), `date` (date), `user_id` (integer)

To accomplish this, use the Elasticsearch Create Index API. You can make requests against this API using tools like cURL, Postman, or Kibana Dev Tools.

The request should look something like this:

```bash
PUT /test_index
{
  "settings" : {
      "number_of_shards" : 1,
      "number_of_replicas" : 0
  },
  "mappings" : {
      "properties" : {
          "title" : { "type" : "text" },
          "date" : { "type" : "date" },
          "user_id" : { "type" : "integer" }
      }
  }
}

