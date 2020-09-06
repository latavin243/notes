# Thrift Generate Golang Code
```bash
docker run -v "$PWD:/data" thrift thrift -o /data --gen go /data/<something>.thrift
sudo chown -R <group>:<user> gen-go

# move code in gen-go/ for further usage
# to skip golang static code check, add `// revive:disable` at the first line
```