---
title: redis_list
type: output
---

<!--
     THIS FILE IS AUTOGENERATED!

     To make changes please edit the contents of:
     lib/output/redis_list.go
-->


Pushes messages onto the end of a Redis list (which is created if it doesn't
already exist) using the RPUSH command.

```yaml
output:
  redis_list:
    url: tcp://localhost:6379
    key: benthos_list
    max_in_flight: 1
```


## Performance

This output benefits from sending multiple messages in flight in parallel for
improved performance. You can tune the max number of in flight messages with the
field `max_in_flight`.

## Fields

### `url`

`string` The URL of a Redis server to connect to.

```yaml
# Examples

url: tcp://localhost:6379
```

### `key`

`string` The key of a Redis list.

### `max_in_flight`

`number` The maximum number of messages to have in flight at a given time. Increase this to improve throughput.

