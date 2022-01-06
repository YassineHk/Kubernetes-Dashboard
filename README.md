#### install dashboard
```
kubectl apply -f dashboard.yml
```
#### add admin role token
```
kubectl apply -f admin-role.yml
```
#### get token for admin role
```
kubectl get secret -n kubernetes-dashboard $(kubectl get serviceaccount admin-user -n kubernetes-dashboard -o jsonpath="{.secrets[0].name}") -o jsonpath="{.data.token}" | base64 --decode
```
#### install kube-metric
```
kubectl apply -f kube-metric.yml
```


