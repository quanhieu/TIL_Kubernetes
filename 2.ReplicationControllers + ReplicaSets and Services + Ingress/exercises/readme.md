# ReplicationControllers + ReplicaSets and Services + Ingress

### Lab requirement

```vi
- Thực hiện deploy 2 webserver nginx và apache bằng ReplicaSet Resource

- Thực hiện tạo Service NodePort cho Nginx và ClusterIP cho Apache

- Tạo Ingress có domain dashboard.me path /hello-world để trỏ vào nginx. Hay khi vào browser gõ dashboard.me/hello-world request sẽ được trỏ vào nginx.

- Tạo Ingress có domain apache2-webserver.com path /me trỏ vào apache service. Hay khi vào browser gõ apache2-webserver.com/ sẽ trỏ về apache pod.
```

***

