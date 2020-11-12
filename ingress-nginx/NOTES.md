> kubectl apply -f https://raw.githubusercontent.com/kubernetes/ingress-nginx/controller-v0.41.0/deploy/static/provider/baremetal/deploy.yaml


> ## https://kind.sigs.k8s.io/docs/user/ingress/
> https://kind.sigs.k8s.io/docs/user/ingress/


## add repo

> helm repo add stable http://mirror.azure.cn/kubernetes/chartse 
> helm repo add incubator http://mirror.azure.cn/kubernetes/charts-incubator/
> helm repo add stable  https://kubernetes.oss-cn-hangzhou.aliyuncs.com/charts/
> helm repo add stable https://burdenbear.github.io/kube-charts-mirror/

## Install via helm
> helm repo add ingress-nginx https://kubernetes.github.io/ingress-nginx
> helm repo add stable https://charts.helm.sh/stable
> helm repo update
> helm install [RELEASE_NAME] ingress-nginx/ingress-nginx
> https://artifacthub.io/packages/helm/ingress-nginx/ingress-nginx
