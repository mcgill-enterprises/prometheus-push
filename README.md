# prometheus-push
Examples for Prometheus PushGateway Development

```
kubectl create  -f prometheus-deployment.yaml 

kubectl get deployments --namespace=monitoring

kubectl get pods --namespace=monitoring

kubectl port-forward ${PROMETHEUS} 8080:9090 -n monitoring
```

## Java

https://prometheus.github.io/client_java/io/prometheus/client/exporter/PushGateway.html

## Simple usage of push metrics

```

 kubectl port-forward ${PUSHGATEWAY} 9091:9091 -n monitoring 
```

```
echo "some_metric 3.14" | curl --data-binary @- http://localhost:9091/metrics/job/some_job
curl http://localhost:9091/metrics
```
 
```
# TYPE some_metric untyped
some_metric{instance="",job="some_job"} 3.14
```
