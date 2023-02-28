# DEM⭕
The demo is used to deploy a super-simple web application for testing purposes - 
primarily to test the accessibility of the application in your cluster. The whole 
demo uses only the standard `busybox` image and the whole configuration is 
in one `demo.yaml` file, so if you need to make modifications, you don't need to 
configure other technologies.

The goal of this project is to provide a demo for different versions of ingress 
and service type LoadBalancer.

## Quickstart
for ingressv1 use this:
```shell
kubectl apply -f https://raw.githubusercontent.com/kuritka/demo/main/ingressv1/demo.yaml
```

```shell
kubectl delete -f https://raw.githubusercontent.com/kuritka/demo/main/ingressv1/demo.yaml
```

Currently we support
- ingressv1
- ingressv1beta1
- loadbalance

ingress is configured to host `demo.cloud.example.com`

## Contribution
any contribution is welcome.
