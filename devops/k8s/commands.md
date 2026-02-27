--dry-run:

| client              | server                    |
| ------------------- | ------------------------- |
| Local validation    | Real cluster validation   |
| No API call         | API server is contacted   |
| No RBAC check       | RBAC is checked           |
| No admission checks | Admission controllers run |
| Faster              | More realistic            |



create a deployment with dry-run that generate a yaml:
kubectl create deployment ouwais-deployment --image=nginx --replicas=3 --dry-run=client -o yaml > deployment.yaml


pods: kubectl run
deployment and namespace: kubectl create ...