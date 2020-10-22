# helm


Helm is a packaging tool for kubernetes application.

Helm chart represents resources neccessary for deploying applications on a kubernetes cluster. charts cab be a single microservice or it full stack for microservices, web frontend, caching, databases.

helm client runs locally for charts deployment.

helm binary from [release page](https://github.com/helm/helm/releases)

### step 1: installation

from binary release page download the desired version [release page](https://github.com/helm/helm/releases)

```
curl https://get.helm.sh/helm-v3.3.1-linux-amd64.tar.gz > helm.tar.gz
tar -xvf helm.tar.gz
cd linux-amd64 
sudo mv helm /usr/local/bin
```

**or** install through script which can be installed locally with following commands.  

```
$ curl -fsSL -o get_helm.sh https://raw.githubusercontent.com/helm/helm/master/scripts/get-helm-3
$ chmod 700 get_helm.sh
$ ./get_helm.sh
```  

run the command `helm init` to initialise helm. exception to run this command to update helm `helm init --upgrade`   

`helm version`check the version   

`which helm` to check the path location   

### step 2: adding repository

create a director by anyname `mkdir helm` and change dir in `cd helm`  
`helm search repo` to search the repo, then add repo with below command.
`helm repo add <name> <link>`  
`helm repo list` check repo list  
`helm repo update` update repo  

### step 3: installation of helm package

`helm search apache` list the apache packages    
`helm install apache stable/apache` should the "helm chart is deprecated" message followed with services.   
`helm status apache` to check the status and reload the configuration.

### step 4: customise the chart
`helm show values stable/apache` customise the chart if neccessary before deploying with the yaml file (config.yaml).  
`helm install -f config.yaml stable/mariadb --generate-name`  




