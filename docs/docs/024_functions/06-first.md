---
sidebar_label: first
---

# first(iterable)

### Input
An iterable.

### Output
The first item of the iterable.

### Example
```yaml
actions:
-   name: keep-slack
    foreach: "{{steps.this.results}}"
    condition:
    - type: threshold
      value: "keep.first(keep.split({{ foreach.value }}, ' '))"
      # each line looks like:
      # ' 64 2023-02-09 20:08:16,773 INFO: uvicorn.access -: 127.0.0.1:53948 - "GET /test2 HTTP/1.1" 503 Service Unavailable'
      # where the "64" is the number of the
      compare_to: 70
```
