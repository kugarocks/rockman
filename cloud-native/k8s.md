# Intro

K8S - Container orchestration platform

---

## Rollout Restart

```bash {copyable}
kubectl rollout restart deploy/foo
```

```bash {copyable}
kubectl rollout restart daemonset/foo
```

---

## Port Forward

Service

```bash {copyable}
kubectl port-forward svc/foo 8080:8080
```

Pod

```bash {copyable}
kubectl port-forward pod/foo 8080:8080
```

---

## Get MySQL Password

```bash {copyable}
kubectl get secret mysql -o jsonpath="{.data.mysql-root-password}" | base64 -d; echo
```

---

## Get PV Reference

foo is pv name

```bash {copyable}
kubectl get pvc -A -o custom-columns="NAMESPACE:.metadata.namespace,NAME:.metadata.name,VOLUME:.spec.volumeName" | grep foo
```

---

## Delete PVC

```bash {copyable}
kubectl delete pvc foo
```

```bash {copyable}
kubectl get pvc | grep 'foo' | awk '{print $1}' | xargs kubectl delete pvc
```

---

## Scale Resources

Deployment

```bash {copyable}
kubectl scale deploy foo --replicas=1
```

StatefulSet

```bash {copyable}
kubectl scale sts foo --replicas=1
```

---

## Get Pods Node Info(IP)

```bash {copyable}
kubectl get pods -o=wide | grep ingressgateway | awk '{print $1, $2, $3, $6, $7}' | while read pod_name ready status pod_ip node_name; do
    node_info=$(kubectl get nodes -o=wide | awk -v node="$node_name" '$1 == node {print $6}')
    echo -e "${pod_name}\t${pod_ip}\t${node_name}\t${node_info}\t${status}"
done
```

```txt {title="kubectl get pods -o=wide"}
NAME  READY  STATUS  RESTARTS  AGE  IP  NODE
foo   1/1    Runn..  0         18d  ..  ..
```

```txt {title="kubectl get nodes -o=wide"}
NAME  STATUS  ROLES  AGE  VERSION  INTERNAL-IP  EXTERNAL-IP
bar   Ready   ...    18d  v1.28.3  10.125.2...  <none>
```

---

## Cluster Start Time

```bash {copyable}
kubectl get pods -n kube-system -l component=etcd -o=jsonpath='{.items[0].status.startTime}'; echo
```

---

## Get Node CIDR

```bash {copyable}
kubectl get nodes -o custom-columns="NODE:.metadata.name,CIDR:.spec.podCIDR"
```

---

## Get IPPool

```bash {copyable}
kubectl get ippool -n kube-system
``` 

```bash {copyable}
kubectl describe ippool default-ipv4-ippool -n kube-system
``` 
