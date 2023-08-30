1. 
```
k taint node gke-cluster-1-default-pool-784c2f42-8l6m node-type=production:NoSchedule
k run test --image=busybox --replicas 5 -- sleep 9999
```