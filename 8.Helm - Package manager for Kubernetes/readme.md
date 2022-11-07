
```yaml

helm version

# Add bitnami chart
helm repo add bitnami https://charts.bitnami.com/bitnami

helm repo list

# Search chart in repo
helm search repo mysql

# Search on internet
helm search hub mysql
```

```yaml
# Create namespace
k create ns mysql
k get ns

# Install mysql chart
helm install mysql bitnami/mysql -n mysql

k get po -n mysql
k describe po mysql-0 -n mysql
k get po -n mysql -w

# Check status
helm status mysql -n mysql

# Exec into mysql
echo $MYSQL_ROOT_PASSWORD

kubectl run mysql-client --rm --tty -i --restart='Never' --image  docker.io/bitnami/mysql:8.0.31-debian-11-r0 --namespace mysql --env MYSQL_ROOT_PASSWORD=$MYSQL_ROOT_PASSWORD --command -- bash

mysql -h mysql.mysql.svc.cluster.local -uroot -p"$MYSQL_ROOT_PASSWORD"
```

```yaml
# Generate helm chart
helm create test-application

helm install test-app test-application -f ./test-application/values.yaml

helm upgrade test-app test-application -f ./test-application/values.yaml
```

```
# Helm chart for production
k create ns production

helm instal test-app test-application -f ./test-application/value-production.yaml -n production
```

```
# List
helm list

helm history test-app

# Rollback -> helm rollback <RELEASE_NAME> <REVISION>
helm rollback test-app

# Delete -> helm delete/uninstall <RELEASE_NAME>
helm delete test-app
```
