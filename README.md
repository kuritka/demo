# Ingress DEM⭕

<div align="center">
 <img class="centerdoge" width="200px" alt="doge png" src="https://github.com/Lietsaki/Who-Is-Doge/blob/master/Images/Main%20Doge.png?raw=true">
</div>

The demo is used to deploy a super-simple web application for testing purposes.
The goal of this project is to test accessibility for different versions of ingresses
and service type LoadBalancer. The whole demo uses only the standard `busybox` image and the whole configuration is 
in one `demo.yaml` file. The advantage of this is that you only need to copy-paste the command into the terminal 
to run the demo. In practice, you don't even need to clone the repository to run the demo.

## Quickstart
for `ingressv1` use command below, but you can apply different ingress versions:
```shell
DEMO_HOST=whatever.demo.cloud.example.com && \
DEMO_DIR=networking.k8s.io-v1 && \
kubectl apply -f https://raw.githubusercontent.com/kuritka/demo/main/$DEMO_DIR/demo.yaml && \
kubectl  -n demo patch ingress demo-ingress --type=json \
-p='[{"op": "replace", "path": "/spec/rules/0/host", "value":"'$DEMO_HOST'"}]'
```

```shell
export DEMO_DIR=networking.k8s.io-v1 && \
kubectl delete -f https://raw.githubusercontent.com/kuritka/demo/main/$DEMO_DIR/demo.yaml
```


## Ingress genesis
Since k8s@1.22 the Ingress with version `extensions/v1beta1` nor `networking.k8s.io/v1beta1` 
are no longer supported. The only supported version is now `networking.k8s.io/v1`
Ingress@v1 was there since 1.19. See [[1]](https://cloud.google.com/kubernetes-engine/docs/deprecations/apis-1-22)


## Support

- networking.k8s.io-v1
- networking.k8s.io-v1beta1
- extensions-v1beta1
- ~~ServiceType: Loadbalancer~~

ingress is configured to host `demo.cloud.example.com`. You have to change it if you are 
testing against another host.

## port-forward
Although it is a secondary thing, it is good to see that the application runs at least port-forward. Run the following command and type http://localhost:8080 into your browser. If nothing is running on port 8080, you should see the demo. 

```shell
kubectl -n demo port-forward deployment/web-app 8080:8404
```

## Contribution
any contribution is welcome.
