# Mediawiki POD's with statci pod names and Resource limit

We can deploy POD's with static names also we can apply resource into pod's manifest.

    $ kubectl apply -f mediawiki_pod-a.yaml
    $ kubectl apply -f mediawiki_pod-b.yaml
    $ kubectl apply -f mediawiki_pod-c.yaml

We can access POD by exposing it.

    $ kubectl expose pod/pod-a --port=8081 --target-port=80 --type=NodePort

Alos below file can be used.

    $ kubectl apply -f static-pod-a-svc.yaml
