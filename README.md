# ELK stack deployment in kubernetes or minikube

__requirement__:
- helm
- kubernetes cluster or minikube

__Install the helm chart to the minikube__
```shell
helm install elk-auto . --set global.hostIp=$(minikube ip)
```

__Port forward for minikube if you want remote access kibana from other machines in you LAN__
```shell
ssh -i ~/.minikube/machines/minikube/id_rsa docker@$(minikube ip) -L \*:31997:0.0.0.0:31997
```
And don't forget to allow traffic on port 31997
```shell
sudo ufw allow 31997/tcp
```