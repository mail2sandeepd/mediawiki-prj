# Mediawiki in Stateful set 

We can deploy application in stateful set as well, which will help us to get pod name consistent.

    $ kubectl apply -f mediawiki_statefulset.yaml

We require database for above deployment which also can be deployed in statefulset or deployment can be used.

------------------------------------------------------------------------------------------------

# Mediawiki POD's with statci pod names and Resource limit Stateful set 

