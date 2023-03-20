# andela-helm 

# Prerequisites

* Helm installed in kubernetes cluster (version v3.8.2 or later)

# Steps

Step 1: **helm create andela**

this command will generates a new Helm chart template with a basic directory structure and set of default files.

Step 2: Inside the helm-templates folder it should contains all the needed kubernetes resources as a **YAML** file to install our application under cluster.In our case it contains configmap,hpa,service,ingress,deployment.yaml files.

Stpe 3:  **kubectl create namespace andela**

kubectl create namespace command will help us to create a **namespace** under kubernetes cluster.

Step 4: **helm upgrade --install andela-springboot-app -n andela . -f ../andela-apps/andela-springboot/values.yaml**

This command is to install a new helm chart under the newly created namespace.**andela-springboot-app** is the user defined **chart name** to be installed.
we have to run this command from the template folder where the chart.yaml present.

Step 5: **kubectl get all -n andela**

This command will give all the details about the kubernetes resources installed by helm install command under the specified namespace.


 
