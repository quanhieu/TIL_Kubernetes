## Introduce k8s

### Lab requirement

```vi
- Tạo namespace mới với tên của bạn, triển khai tất cả các pod ở yêu cầu sau trên namespace này.

- Đánh label cho namespace này với giá trị namespace-test là true.

- Tạo các pod với image đã build trong học phần Docker

- Từ các pod đã tạo thử gọi đến dịch vụ của nhau, ví dụ từ ubuntu gọi đến nginx webserver.
```

***

## Create namespace

`
kubectl create namespace namespace-test
`

## Init [pod](./lab.yml) - nginx-3

`
k apply -f ./lab.yml
`

## Get all pods

`
k get pods -A
`

## Filter pod nginx-3

`
k get pods -A | grep nginx-3
`

## Port Forwarding to local

`
kubectl port-forward -n default pod/nginx-3 80:3000
`

## Check port forwarding succeeded

`
nc -zvv localhost 3000
`
