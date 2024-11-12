
# k8s-service-deployment

This folder contains configurations for a Kubernetes **Deployment** and **Service**.

## Kubernetes Objects

### Deployment
The `Deployment` object defines a blueprint for deploying and managing a set of identical Pods. It controls the number of replicas, the container image to run, and other properties. The `deployment.yaml` file here ensures that a specified number of replicas (Pods) are running at any time.

### Service
The `Service` object provides a stable endpoint to access the set of Pods created by the Deployment. This configuration allows other services or users to access the application, regardless of changes in the underlying Pods.

## File Overview
- **deployment.yaml**: Configures the Deployment with specified replicas, container image, and labels.
- **service.yaml**: Exposes the Deployment Pods through a Service on a defined port.

## Commands
1. Apply Deployment and Service:
   ```sh
   kubectl apply -f deployment.yaml
   kubectl apply -f service.yaml
   ```

2. Verify Deployment and Service:
   ```sh
   kubectl get deployments
   kubectl get services
   kubectl get pods
   ```

3. Clean up resources:
   ```sh
   kubectl delete -f deployment.yaml
   kubectl delete -f service.yaml
   ```
