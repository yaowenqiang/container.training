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

> kubectl proxy --port=8888 --address=0.0.0.0 --accept-hosts=.*

# update cluster


> skip TLS verification

> kubectl config set-cluster kubernetes --server=https://X.X.X.X:6443
> kubectl config set-cluster kubernetes --insecure-skip-tls-verify

# completion 
>  yum install -y bash-completion
> source /usr/share/bash-completion/bash_completion
> source <(kubectl completion bash)
> echo "source <(kubectl completion bash)" >> ~/.bashrc # 在您的 bash shell 中永久的添加自动补全
> alias k=kubectl
> complete -F __start_kubectl k


# networking 

> docker inspect --format '{{ .State.Pid }}' container-id-or-name
> 
> nsenter -t pid -n ip addr

# Update cluster  server address 

> kubectl config set-cluster kubernetes --server=https://X.X.X.X:6443
> kubectl config set-cluster kubernetes --insecure-skip-tls-verify

## dump resource to yml

> kubectl get deploy/rng -o yaml --export >rng.yml

# install yq

> wget https://github.com/mikefarah/yq/releases/download/3.4.0/yq_linux_amd64 -O /usr/bin/yq &&\
    chmod +x /usr/bin/yq


# Checking current rollout parameters

# kubectl get deploy -o json |
        jq ".items[] | {name:.metadata.name} + .spec.strategy.rollingUpdate"

> wget https://github.com/wercker/stern/releases/download/1.11.0/stern_linux_amd64

# use stern go view  logs of multi podes

> stern --tail 1 --timestamps --all-namespaces podname



## deploy application

> REGISTRY=yaowenqiang
> export REGISTRY
> export TAG=v0.1
> kubectl create deployment redis --image=redis
> for SERVICE in hasher rng webui worker; do
> kubectl create deployment $SERVICE --image=$REGISTRY/$SERVICE:$TAG
done
> kubectl expose deployment redis --port 6379
> kubectl expose deployment rng --port 80
> kubectl expose deployment hasher --port 80


## filter kubectl run  logs
> sern -l run


## filter kubectl create deployment logs
> stern -l app 


# helm create charts

> helm create dockercoins


## change context

> kubectl config set-context --current --namespace=blue
> kubectl config get-contexts


## kubectx && kubens

> wget https://github.com/ahmetb/kubectx/releases/download/v0.9.1/kubectx_v0.9.1_linux_x86_64.tar.gz
> wget https://github.com/ahmetb/kubectx/releases/download/v0.9.1/kubens_v0.9.1_linux_x86_64.tar.gz


## kube-ps1

> git clone git@github.com:yaowenqiang/kube-ps1.git
> source /path/to/kube-ps1.sh
> PS1='[\u@\h \W $(kube_ps1)]\$ '


## install krew


```
(
  set -x; cd "$(mktemp -d)" &&
    curl -fsSLO "https://github.com/kubernetes-sigs/krew/releases/latest/download/krew.tar.gz" &&
      tar zxvf krew.tar.gz &&
        KREW=./krew-"$(uname | tr '[:upper:]' '[:lower:]')_$(uname -m | sed -e 's/x86_64/amd64/' -e 's/arm.*$/arm/')" &&
	  "$KREW" install krew
	  )

```



## install skaffold

> wget https://github.com/GoogleContainerTools/skaffold/releases/download/v1.16.0/skaffold-linux-amd64

## install Cilium
> https://docs.cilium.io/en/stable/gettingstarted/k8s-install-default/

## ingress
> https://kubernetes.io/zh/docs/concepts/services-networking/ingress/

# treafik
> https://doc.traefik.io/traefik/v1.7/user-guide/kubernetes/
