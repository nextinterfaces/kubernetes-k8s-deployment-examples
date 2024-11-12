
# k8s-service-deployment-pods-ingress

This folder contains configurations for a Kubernetes **Deployment**, **Service**, **Pod**, and **Ingress**.

## Kubernetes Objects

### Pod
Defines a single instance of a running application container.

### Deployment
Manages multiple replicated Pods, ensuring a specified number of replicas are always running.

### Service
Exposes the set of Pods created by the Deployment for internal or external access. In this setup, the Service acts as a backend for the Ingress.

### Ingress
The `Ingress` object manages HTTP and HTTPS access to services within the cluster, offering load balancing, SSL termination, and host-based routing.

## File Overview
- **pod.yaml**: Configures a standalone Pod.
- **deployment.yaml**: Manages Pods with scaling and rolling update capabilities.
- **service.yaml**: Exposes the Deployment Pods.
- **ingress.yaml**: Routes external traffic to the Service based on specified rules.

## Commands
1. Apply configurations:
   ```sh
   kubectl apply -f pod.yaml
   kubectl apply -f deployment.yaml
   kubectl apply -f service.yaml
   kubectl apply -f ingress.yaml
   ```

2. Verify resources:
   ```sh
   kubectl get pods
   kubectl get deployments
   kubectl get services
   kubectl get ingress
   ```

3. Clean up resources:
   ```sh
   kubectl delete -f pod.yaml
   kubectl delete -f deployment.yaml
   kubectl delete -f service.yaml
   kubectl delete -f ingress.yaml
   ```

## Note
Ensure that an Ingress controller is installed in your Kubernetes cluster to enable Ingress functionality.
