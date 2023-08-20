k rolling-update kubia-v1 kubia-v2 --image=luksa/kubia:v2
k patch deployment kubia -p '{"spec":{"minReadySeconds":10}}'
k set image deployment kubia nodejs=luksa/kubia:v2
k set image deploy kubia nodejs=luksa/kubia:v4
k rollout pause deployment kubia