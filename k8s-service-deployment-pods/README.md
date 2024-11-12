
# k8s-service-deployment-pods

This folder includes configurations for a Kubernetes **Deployment**, **Service**, and a standalone **Pod**.

## Kubernetes Objects

### Pod
A `Pod` is the basic unit in Kubernetes that runs a single instance of a container. The `pod.yaml` file allows us to define a standalone Pod outside of a Deployment, which can be useful for single-instance applications.

### Deployment
The `Deployment` ensures a specified number of Pods are running based on a template. It’s useful for scaling applications and managing Pods.

### Service
A `Service` exposes both the Deployment and standalone Pod. It provides a stable IP address and DNS name for a group of Pods, allowing them to be accessed by other applications or users.

## File Overview
- **pod.yaml**: Defines a standalone Pod running a specified container.
- **deployment.yaml**: Manages a set of replicated Pods with scaling capabilities.
- **service.yaml**: Provides network access to the Deployment Pods and/or standalone Pod.

## Commands
1. Apply each file:
   ```sh
   kubectl apply -f pod.yaml
   kubectl apply -f deployment.yaml
   kubectl apply -f service.yaml
   ```

2. Verify objects:
   ```sh
   kubectl get pods
   kubectl get deployments
   kubectl get services
   ```

3. Clean up resources:
   ```sh
   kubectl delete -f pod.yaml
   kubectl delete -f deployment.yaml
   kubectl delete -f service.yaml
   ```
