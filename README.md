# very-simple-web-server-k8s

Synopsis
----------

This helm chart will deploy simple nginx http server with index.html stored in config map.

It can be deployied in any existing kubernetes cluster. GKE for example.

Prerequisites
----------

- Clone repo
- Configure your kubernetes context

Installing
----------

```
helm install very-simple-web-server-k8s very-simple-web-server-k8s
```


Updating
----------
 - Update website/index.html to change index.html
 - Run helm upgrade command:

```
helm upgrade very-simple-web-server-k8s very-simple-web-server-k8s
```

Check the result
----------
- Check LoadBalancer IP address and open it in a browser
```
kubectl get svc | grep very-simple-web-server-k8s 

URL=http://$(kubectl get svc | grep very-simple-web-server-k8s | awk '{print $4}')/index.html;
echo $URL

```