Kubernetes Deployment Documentation

This document outlines the deployment process for the microservice in Kubernetes, using Nginx as a load balancer and external MongoDB and Redis services provided by cloud providers.

# Key Kubernetes Components

1. Deployment
    Manages the application pods, ensuring the desired number of replicas are running and automatically replacing failed pods.

    Resource Requests and Limits
        - Requests: Minimum guaranteed resources for a pod (e.g., CPU: 250m, Memory: 256Mi).
        - Limits: Maximum resources a pod can consume (e.g., CPU: 500m, Memory: 512Mi).

2. Nginx Load Balancer
    Nginx acts as a reverse proxy and load balancer, distributing incoming traffic to the application pods.

3. Service
    Exposes the application within the cluster and forwards traffic from the Nginx load balancer.

4. Horizontal Pod Autoscaler (HPA)
    Automatically adjusts the number of pods based on resource utilization.


# Scalability Strategy

1. Horizontal Pod Autoscaling (HPA)

Purpose: Automatically adjusts the number of running pods based on CPU or memory usage.

Configuration:

Minimum replicas: 3

Maximum replicas: 10

Target CPU utilization: 75%

2. Cluster Autoscaler

Ensures nodes are added or removed based on resource requirements.

Works in tandem with HPA to handle increased workloads efficiently.



# Deployment Steps

1. Apply ConfigMap

    kubectl apply -f nginx-config.yaml

2. Deploy Application, Nginx Load Balancer and Autoscaling

    kubectl apply -f deployment.yaml
