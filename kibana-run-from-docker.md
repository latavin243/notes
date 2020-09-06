# Run Kibana From Docker

```bash
docker run \
  --name kibana \
  -p 5601:5601 \
  --link elasticsearch_container:elasticsearch_alias \
  -e "ELASTICSEARCH_URL=<some_url>" \
  kibana:6.5.4
```