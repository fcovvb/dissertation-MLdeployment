# A Set of Practicess and Architectures for ML Deployments for Small and Medium Companies (SMBs)
## Disclaimer
This document was generated through a process of researching ML Deployment technologies (API-Server, Docker, Kubernetes, Apache Spark, Seldon Core, Kubeflow, and MLFlow) and experimentation deploying some of the already mentioned solutions. The entire process was designed and performed by one person, and many other technologies were not considered for this experiment because the limited amount of time and knowledge needed to explore more alternative.

## Why is this relevant
1.	Quickly deploy a Machine Learning Model using Open-Source solutions.
2.	Manage the model versioning, governance, and traceability of the process.
3.	Auto-scalability, to ensure cost and performance efficiency of the system.
4.	Be able to deploy models using similar technologies used in the building and training stages.
5.	Automate manual processes to leave more time for Data Science, and less for configuration and scalability of the platform.

## SMBs Specific Challenges
1. SMBs have limited financial resources.
2. SMBs have difficulties acquiring and retaining digital talent.
3. 3rd Party Propietary Softwares/Solutions can generate a Lock-in and, in many cases, the knowledge acquired to use one service is not transferable to other services.

## Best Practicess
1. The system should have a model repository, that allows Accessing and Versioning them. --> This will allow you to compare your models and choose which one to deploy depending on a desired 
   metric(r2, F1, accuracy,etc.)/performance(time to process).
2. Have a system with Traceability capabilities, where you can trace a prediction back to the model and data that generated it. -->
3. Monitor your Models in Testing and Production. -->
4. Look for solutions that help you to deploy faster and perform continuous updates. --> Time pases, your data gets outdated. so your model.

## Recommended Architecture Diagram to Implement
### Description of the system
The system, is an implementation of Seldon Core, that uses Kubernetes as the main platform to maintain all the services needed to deploy a machine learning model. Kubernetes hosts and orchestrates Seldon Core, Istio, and the models that Seldon will be in charge of deploying.
This solution will allow Data Scientist to deploy........................ACAAAAAAAAAAAAAAAAAAAA
Orchestrate, Be robust against app crashes, scale up and down containers, making easy to scale the node up and down by adding new nodes to the system.

### Diagram Figure
![Architecture 1](https://dissertationfco.blob.core.windows.net/dissfco/1stArchitecture.png?)

### Table of the technologies displayed in the architecture diagram

| Technology | Use case |
| --- | --- |
| Kubernetes | Platform used to deploy and orchestrate ML Models, Istio, and Seldon Core. |
| Kubectl | Is a command-line interface installed locally in the cluster administrator’s computer to manage Kubernetes and define Deployment Manifests. |
| Cloud Storage | We will be using a Cloud Storage as a repository for Model Binaries (e.g., TensorFlow, Scikit Learn, Pytorch), so Seldon Core can access them when deploying the service. |
| Seldon Core | Is the deployment solution for ML Models, that also is deployed inside Kubernetes. |
| Istio | Is the service mesh that is in charge of connecting services with other services or ingress/egress endpoints. |
| Istioctl | Is a command-line interface to manage the Istio installation inside a Kubernetes platform. |
| Helm | Helm is a package manager to automate and facilitate deployments in Kubernetes. |
| Lens (optional) | User interface used to monitor and debug deployments/pods in Kubernetes. |
