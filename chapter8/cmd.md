k exec -it downward -- env|sort
k exec -it downward -- cat /etc/downward/labels
k get pod downward --show-labels
k label pod downward foo1=bar1
k cluster-info
k proxy
10.8.128.1

k exec -it curl -- curl -k https://kubernetes.default.svc.cluster.local
k exec -it curl -- curl --cacert /var/run/secrets/kubernetes.io/serviceaccount/ca.crt https://kubernetes.default.svc.cluster.local
TOKEN=$(cat /var/run/secrets/kubernetes.io/serviceaccount/token)
curl -H "Authorization: Bearer $TOKEN" --cacert /var/run/secrets/kubernetes.io/serviceaccount/ca.crt https://kubernetes.default.svc.cluster.local
 k create clusterrolebinding permissive-binding --clusterrole=cluster-admin --group=system:serviceaccounts
 NS=$(cat /var/run/secrets/kubernetes.io/serviceaccount/namespace)
 curl -H "Authorization: Bearer $TOKEN" --cacert /var/run/secrets/kubernetes.io/serviceaccount/ca.crt https://kubernetes.default.svc.cluster.local/api/v1/namespaces/$NS/pods



