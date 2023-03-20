# andela-helm

# what is helm?

  Helm is a package manager for Kubernetes that simplifies the deployment and management of applications and services. It allows you to define, install, and upgrade complex Kubernetes applications with ease, by providing a templating system for YAML files that describe the various Kubernetes resources required to run your application.

  With Helm, you can define a "chart", which is a collection of files that describe the Kubernetes resources that make up an application or service, along with any necessary configuration values. Helm can then use these charts to deploy the application or service to a Kubernetes cluster.

  Helm also supports versioning, dependency management, and rollback of deployments. It can also be extended with plugins to add additional functionality. Overall, Helm is a powerful tool for managing complex Kubernetes deployments and simplifying the management of cloud-native applications.

------------------------------------------------------------------------------------------------------------------------------------------------------
# How we using helm?

  Here we using helm charts to install our applications in kubernetes cluster.Our helm chart should contains needed resources to be installed under our kubernetes cluster.In our repository we followed helm templating approach,helm-templates folder consists template YAML files for like Deployment,Service,ingress etc., And andela-apps consists of applications values.yaml file.In our case the andela-apps folder contains another folder called andela-springboot,so we are having one values.yaml file there inside andela-springboot folder to run our install our application under kubernetes cluster.

------------------------------------------------------------------------------------------------------------------------------------------------------
# Steps to install the application using helm

* We Need to create a namespace in our kubernetes cluster to install our application.Using the command like (kubectl create namespace andela)
* Then we have to install the application using helm install command from the helm-templates folder like this (helm upgrade --install andela-springboot-app -n andela . -f ../andela-apps/andela-springboot/values.yaml)
* The above command will help us to install or upgrade our helm chart.
* Once the helm chart installed successfully we can check our created kubernetes resources using our templates by this command (kubectl get all -n andela)
----------------------------------------------------------------------------------------------------------------------------------------------------------

