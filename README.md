# Assignment46 -Voting App
1. Once the voter pod was deleted, it was respawned again with a different id. but front end was fine. and back end was also fine. The voting count remained correct.

2. Once the worker pod was deleted, it was respawned again with a different id. but front end was fine. and back end was also fine. The voting count remained correct.

3. On deleting the db pod, the worked pod showed an error briefly , but it came back to running state. The worker pod and result pod restart count increased to make the program work. Without restarting, the old DB connection wouldnt have worked. 
``` 
[root@ip-172-31-8-242 ~]# kubectl delete po db-b54cd94f4-789n7
pod "db-b54cd94f4-789n7" deleted
[root@ip-172-31-8-242 ~]# kubectl get po
NAME                      READY   STATUS    RESTARTS   AGE
db-b54cd94f4-pzw7l        1/1     Running   0          59s
redis-868d64d78-pl7mj     1/1     Running   0          2d20h
result-5d57b59f4b-6kqgt   1/1     Running   2          2d20h
vote-94849dc97-k577n      1/1     Running   0          2d20h
worker-dd46d7584-44727    1/1     Running   1          88s
```
4. When DB pod is deleted, the data goes away along with it. The vote count from previous instance is gone. 
5. If we restart a POD, the container restart count is reset. as in the case of worker-dd46d7584-44727
