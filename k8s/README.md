

- Postgres password was generted through imperative command. An example is provided below:
`kubectl create secret generic pgpassword --from-literal PASSWORD=123456`

- To run this project locally using the Nginx ingress controller, you must enable minikube tunnelling
`minikube tunnel`

In previous verison of minikube which were run on a linux VM, you would have only needed the minikube VM IP address to access the services locally.
However, minikube is now run inside a Docker container which creates docker containers inside it. This means you have two layers of networking you must pass through. To resolve this, minikube have create a network tunnel which allows containers like ingress running inside the minikube container to bypass through the stacked network layers.

ingress container | -->   minikube container | --> host network @ localhost
