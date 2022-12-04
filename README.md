# mediawiki-prj

MediaWiki is a free and open-source wiki software. It is used on Wikipedia and almost all other Wikimedia websites.

We are building it for our Kubernetes/OpenShift Deployment.

Build container image uning php:apache as base image

We have build container images, and uploaded to Dockerhub.

 Clone upstream Git repository


    $ mkdir work
    $ cd work
    $ git clone https://github.com/mail2sandeepd/mediawiki-prj.git
    $ cd mediawiki-prj


Build container image and push it to ECR

    $docker build -t <your_image_name> .
    $docker pull 

Note :- Before pushing image into Dockerhub you have to login into registry.

Explanation:


Deploying mediawiki application into Kubernetes/OpenShift, please create namespace/project in cluster before appling manifest.

    $ kubectl apply -f mediawiki_deployment.yaml
    $ kubectl apply -f mediawiki_service.yaml 
    $ kubectl apply -f mediawiki_db_secret.yaml 
    $ kubectl apply -f mediawiki_db_cm.yaml 
    $ kubectl apply -f mediawiki_db_deployment.yaml 
    $ kubectl apply -f mediawiki_db_service.yaml 
  
Open mediawiki for first setup, once mediawiki installation in cpmpleted you will get "LocalSettings.php" file which  needs to be updated as connfig map so it will be avalable for deployment. please create config map for php setting.

    $ kubectl create configmap cm-php-local-setting --from-file LocalSettings.php

Now update mediawiki deployment for your cluster 
    
    $ kubectl apply -f mediawiki_deploymentupdate.yaml
    
   
