```sh
kn default
kubectl apply -f guest-book.yaml
kubectl apply -f es.yaml
kubectl logs es | grep "mode \[basic\] - valid"
kubectl apply -f kibana.yaml
kubectl logs kibana|grep "Status changed from yellow to green"
kubectl apply -f filebeat-kubernetes.yaml
kubectl get pods -n kube-system | grep filebeat
kubectl describe po -l k8s-app=filebeat-dynamic -n kube-system
git clone https://github.com/kubernetes/kube-state-metrics.git kube-state-metrics
kubectl apply -f kube-state-metrics/kubernetes
kubectl get po -l k8s-app=kube-state-metrics -n kube-system
kubectl apply -f metricbeat-setup.yaml
kubectl get pods -n kube-system | grep metricbeat
kubectl apply -f metricbeat-kubernetes.yaml
kubectl get pods -n kube-system | grep metricbeat
kubectl describe po -l k8s-app=metricbeat -n kube-system
```
