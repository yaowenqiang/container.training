# ExternalDNS
> https://github.com/kubernetes-sigs/external-dns

> kubectl run nginx --image=nginx --replicas=1 --port=80
> kubectl expose deployment nginx --port=80 --target-port=80 --type=LoadBalancer
> kubectl annotate service nginx "external-dns.alpha.kubernetes.io/hostname=nginx.example.org."

> 
