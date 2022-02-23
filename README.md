# Kubernetes deployment for simple krakend API Gatway application.

KrakenD is a stateless, distributed, high-performance API Gateway that helps you effortlessly adopt microservices.

This repo hols a kuberneted deployment for KrakenD service along with customizable configmap krakend.json as well as ingress controller.
These manifests are tested against Public IP and microk8s distribution.
But since these are very basic level yaml files, it should work on any kubernetes distribution.

└── k8maifests\n
    ├── configmap.yaml\n
    ├── deployment.yaml\n
    ├── ingress.yaml\n
    └── service.yaml\n

# Deployment
To deploy, make necessary path changes to ingress.yaml and configmap.yaml
Entire krakend.json config file is represneted inside configmap.yaml

For microk8s, the ingressclass annotation is Public by default.
It will be nginx in case of external nginx deployments.

Check the different ingress class availabe on your cluster using
`kubectl get ingressClass`

Rest of the files can be left untouched.

Once config is final,
`kubectl apply -f k8manifests`

This will expose KrakenD API gateway on ingress controller.
