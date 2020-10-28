>  access service via proxy
> curl http://127.0.0.1:8001/api/v1/namespaces/default/services/registry:5000/proxy/v2/_catalog
> kubectl port-forward service/registry 5000
> NODEPORT=5000
> REGISTRY=127.0.0.1:$NODEPORT
> curl $REGISTRY/v2/_catalog
> docker pull busybox
> docker tag busybox $REGISTRY/busybox
> docker push $REGISTRY/busybox
> docker logs deploy/worker

> kill a job
> kill %1 

> kubectl proxy --port=8888 --address=0.0.0.0 --accept-hosts=.*<Paste>

# update cluster


> skip TLS verification

> kubectl config set-cluster kubernetes --server=https://X.X.X.X:6443
> kubectl config set-cluster kubernetes --insecure-skip-tls-verify
