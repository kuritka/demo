# DEM⭕
The demo is used to deploy a super-simple web application for testing purposes - 
primarily to test the accessibility of the application in your cluster. The whole 
demo uses only the standard `busybox` image and the whole configuration is 
in one `demo.yaml` file, so if you need to make modifications, you don't need to 
configure other technologies.

The goal of this project is to provide a demo for different versions of ingress 
and service type LoadBalancer.

## Quickstart
for `ingressv1` use command below, but you can apply different ingress versions:
```shell
kubectl apply -f https://raw.githubusercontent.com/kuritka/demo/main/ingressv1/demo.yaml
```

```shell
kubectl delete -f https://raw.githubusercontent.com/kuritka/demo/main/ingressv1/demo.yaml
```

## Ingress genesis
Since k8s@1.22 the Ingress with version `extensions/v1beta1` nor `networking.k8s.io/v1beta1` 
are no longer supported. The only supported version is now `networking.k8s.io/v1`
Ingress@v1 was there since 1.19. See [[1]](https://cloud.google.com/kubernetes-engine/docs/deprecations/apis-1-22)


## Support
Currently we support
- ingressv1
- ingressv1beta1
- loadbalance

ingress is configured to host `demo.cloud.example.com`

## Contribution
any contribution is welcome.
