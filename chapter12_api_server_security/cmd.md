1. token
```
k exec -it curl-custom-sa -- cat /var/run/secrets/kubernetes.io/serviceaccount/token
```
2. test
```
k exec -it curl-custom-sa -c main -- curl localhost:8001/api/v1/pods
```
3. 
```
k create ns foo
k run test --image=luksa/kubectl-proxy -n foo
k create ns bar
k run test --image=luksa/kubectl-proxy -n bar
```
4. 
```
k create rolebinding test --role=service-reader --serviceaccount=foo:default -n foo
```
5. 
```
curl localhost:8001/api/v1/persistentvolumes
k create rolebinding pv-test --clusterrole=pv-reader --serviceaccount=foo:default -n foo
k create clusterrolebinding pv-test --clusterrole=pv-reader --serviceaccount=foo:default -n foo
```