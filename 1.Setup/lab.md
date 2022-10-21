# What is Kubernetes + Pod + Namespace + Label and Annotation

```en
- Create namespace with your any-name, and implement namespace for all pods.

- Update label for namespace, that namespace-test is true.

- Create pods with image is built by any docker

- All pods is created, try to conversation, example from ubuntu to nginx webserver.
```

```vi
- Tạo namespace mới với tên của bạn, triển khai tất cả các pod ở yêu cầu sau trên namespace này.

- Đánh label cho namespace này với giá trị namespace-test là true.

- Tạo các pod với image đã build trong học phần Docker

- Từ các pod đã tạo thử gọi đến dịch vụ của nhau, ví dụ từ ubuntu gọi đến nginx webserver.
```

```yml
apiVersion: v1
kind: Pod
metadata:
  name: nginx-2
  namespace: devops
  labels:
    namespace-test: true
spec:
  containers:
  - name: nginx
    image: nginx:1.14.2
    ports:
    - containerPort: 80
```
