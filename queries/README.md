# 🔎 Saved Searches

The Elasticsearch searches I use to pull findings out of T-Pot.

## How to run them

1. Open **Elasticvue** (through the SSH tunnel)
2. Go to **Search**
3. Index pattern: `logstash-*`
4. Open **Custom Search** and paste a query
5. Click **Search**, then open the **Aggregations** tab

`"size": 0` means "only show the summary", so the Hits tab stays empty. That's normal.

---

## 1. Top passwords and usernames

```json
{
  "size": 0,
  "query": {
    "query_string": {
      "query": "type:Cowrie AND eventid:\"cowrie.login.failed\""
    }
  },
  "aggs": {
    "top_passwords": {
      "terms": { "field": "password.keyword", "size": 10 }
    },
    "top_usernames": {
      "terms": { "field": "username.keyword", "size": 10 }
    }
  }
}
```

---

## 2. Busiest honeypots, countries and ports

```json
{
  "size": 0,
  "aggs": {
    "top_honeypots": {
      "terms": { "field": "type.keyword", "size": 15 }
    },
    "top_countries": {
      "terms": { "field": "geoip.country_name.keyword", "size": 10 }
    },
    "top_ports": {
      "terms": { "field": "dest_port", "size": 10 }
    }
  }
}
```

---

## 3. Commands attackers typed

```json
{
  "size": 0,
  "query": {
    "query_string": { "query": "eventid:\"cowrie.command.input\"" }
  },
  "aggs": {
    "top_commands": {
      "terms": { "field": "input.keyword", "size": 15 }
    }
  }
}
```

---

## 4. Malware files

```json
{
  "size": 0,
  "query": {
    "query_string": {
      "query": "eventid:\"cowrie.session.file_download\" OR eventid:\"cowrie.session.file_upload\""
    }
  },
  "aggs": {
    "download_urls": {
      "terms": { "field": "url.keyword", "size": 15 }
    },
    "file_hashes": {
      "terms": { "field": "shasum.keyword", "size": 15 }
    }
  }
}
```

---

## 💡 Tips

1. If a search errors with "Fielddata is disabled", add `.keyword` to the field name
2. If a result is empty, the field name might differ. Run a search with `"size": 3` and look at a real record in the Hits tab
3. `doc_count` = how many times that value appeared
