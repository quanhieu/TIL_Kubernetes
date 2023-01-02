
## Init [pod](./lab.yml) - nginx-3

`
k apply -f ./lab.yml
`

## Get all pods

`
k get pods
`

## Port Forwarding to local

`
kubectl port-forward -n default pod/nginx-3 80:3000
`

## Check port forwarding succeeded

`
nc -zvv localhost 3000
`
