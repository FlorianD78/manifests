Installer Minikube  
Installer kubectl  
Lancer minikube avec kube=v1.21.0  
Cloner le repo kubeflow/manifests  
Changer le type de istio-ingressgateway NodePort vers LoadBalancer avec : kubectl get svc istio-ingressgateway -n istio-system -o yaml > svc.yaml  
Installer l'addons ingress-nginx  
Créer l'ingress-nginx sur de pod istio-ingressgateway :  
```
apiVersion: networking.k8s.io/v1
kind: Ingress
metadata:
  name: test-ingress
spec:
  defaultBackend:
    service:
      name: testsvc
      port:
        number: 80
```
Dans un autre terminal : minikube tunnel  
Accès http://IP-ADRESS:PORT
