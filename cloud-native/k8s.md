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
