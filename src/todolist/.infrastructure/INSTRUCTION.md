# Instructions to deploy and test ToDo App

## 1. Apply manifests
```bash
kubectl apply -f .infrastructure/namespace.yml
kubectl apply -f .infrastructure/busybox.yml
kubectl apply -f .infrastructure/todoapp-pod.yml

# 2. Check resources
kubectl get pods -n todoapp
kubectl describe pod todoapp -n todoapp

3. Port-forward to access ToDo app

kubectl port-forward pod/todoapp 8000:8000 -n todoapp

4. Test ToDo app using busybox

kubectl exec -it busybox -n todoapp -- curl http://todoapp:8000/api/health/

