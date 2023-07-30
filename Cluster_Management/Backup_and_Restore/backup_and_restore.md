# 💾 Backup and Restore a Cluster and/or Specific Indices

In this section, we will learn how to backup and restore a cluster and/or specific indices in Elasticsearch.

## 📚 Learning Materials

Here are some resources to help you understand this topic:

- [Snapshot and restore | Elasticsearch Reference [8.1] | Elastic](https://www.elastic.co/guide/en/elasticsearch/reference/current/snapshot-restore.html)
- [How To Backup Elasticsearch Indices and Clusters](https://www.elastic.co/guide/en/cloud/current/ec-restoring-snapshots.html)

## 🛠️ Exercises

1. First, you need to register a repository where the snapshots will be stored. Let's assume you have a shared file system repository. Here is how you can register it:

```bash
PUT /_snapshot/my_backup
{
  "type": "fs",
  "settings": {
    "location": "my_backup_location"
  }
}
```

2. Now you can create a snapshot that includes specific indices. For example, let's backup the `test_index` index:

```bash
PUT /_snapshot/my_backup/snapshot_1?wait_for_completion=true
{
  "indices": "test_index"
}
```

3. If you want to restore the `test_index` index from snapshot, you can do so with the following command:

```bash
POST /_snapshot/my_backup/snapshot_1/_restore
{
  "indices": "test_index"
}
```

Remember to replace `my_backup_location` with the actual path to your backup location. Also, remember to use a tool like cURL, Postman, or Kibana Dev Tools to interact with your Elasticsearch cluster.


