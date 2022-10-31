
```yaml
# start minikube with multiple node
minikube start --nodes 2 -p multinode-demo

docker ps
```

```
- Thực hiện deploy Stateful application sử dụng statefulset resource.
- Ứng dụng là webserver nginx có 3 pods, nội dung được lưu vào pvc
- Khi truy cập mỗi pod thì pod sẽ trả về nội dung “Xin chào đây là pod + số thứ tự"
- Đảm bảo khi xóa pod thì pod mới lên vẫn có thể phản hồi request với nội dung như pod cũ.
```