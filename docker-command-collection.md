# Docker Command Collection

```bash
# build
# under file with Dockerfile
# image tag name e.g. awesome-image:v0.1
docker build -t <image_tag_name> .

# run
docker run \
-v <local_file_path>:<containter_file_path> \
--network host \
<image_tag_name> \
<other_args>

# rename tag
docker tag <image_id> <new_tag_name>

# push
docker push <image_tag_name>
```

