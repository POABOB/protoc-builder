# protoc-builder

## 使用方式

### Build Image


- 打包成鏡像，看後續你有沒有需要上傳Docker Hub
```bash=
docker build --no-cache --pull --force-rm -t poabob/protoc-builder:latest .
```

- Push 到 Dockerhub(Push 前請先有Dockerhub帳號)
```bash=
docker push poabob/protoc-builder:latest
```

### Generate Proto
```bash=
sudo docker run --rm -v $(pwd):$(pwd) -w $(pwd) -t poabob/protoc-builder --proto_path=. --micro_out=. --go_out=:. ./protos/base/base.proto
```
