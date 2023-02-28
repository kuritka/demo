# DEM⭕

<div align="center">
 <img class="centerdoge" width="200px" alt="doge png" src="https://github.com/Lietsaki/Who-Is-Doge/blob/master/Images/Main%20Doge.png?raw=true">
</div>

The demo is used to deploy a super-simple web application for testing purposes.
The goal of this project is to test accessibility for different versions of ingresses
and service type LoadBalancer. The whole demo uses only the standard `busybox` image and the whole configuration is 
in one `demo.yaml` file.


## Quickstart
for `ingressv1` use command below, but you can apply different ingress versions:
```shell
kubectl apply -f https://github.com/kuritka/demo/blob/main/networking.k8s.io-v1/demo.yaml
```

```shell
kubectl delete -f https://github.com/kuritka/demo/blob/main/networking.k8s.io-v1/demo.yaml
```

## Ingress genesis
Since k8s@1.22 the Ingress with version `extensions/v1beta1` nor `networking.k8s.io/v1beta1` 
are no longer supported. The only supported version is now `networking.k8s.io/v1`
Ingress@v1 was there since 1.19. See [[1]](https://cloud.google.com/kubernetes-engine/docs/deprecations/apis-1-22)


## Support

- networking.k8s.io/v1, extensions/v1beta1
- networking.k8s.io/v1beta1
- extensions/v1beta1
- ~~loadbalance~~

ingress is configured to host `demo.cloud.example.com`. You have to change it if you are 
testing against another host.

## Contribution
any contribution is welcome.
