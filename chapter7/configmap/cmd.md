k exec -it fortune-pod-configmap-part-volume -- curl -H "Accept-Encoding: gzip" -I localhost:80
k exec -it fortune-pod-configmap-part-volume -- cat /etc/nginx/conf.d/default.conf

k exec -it fortune-pod-configmap-part-volume -- ls /etc/nginx/conf.d/