## Envoy help
```shell
kubectl exec <envoy-pod> -c istio-proxy curl http://127.0.0.1:15000/help -n istio-system
```

## Export envoy config
```shell
kubectl exec <envoy-pod> -c istio-proxy curl http://127.0.0.1:15000/config_dump -n istio-system
```
