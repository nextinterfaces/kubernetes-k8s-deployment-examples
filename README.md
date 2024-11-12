
# Kubernetes Sample Project

This repository demonstrates a sample Kubernetes setup using **Deployment**, **Service**, **Pod**, and **Ingress** configurations. It provides various configurations to illustrate Kubernetes object management and networking.

## Folder Structure

- **k8s-service-deployment**: Contains a Deployment and Service configuration.
- **k8s-service-deployment-pods**: Adds a standalone Pod configuration in addition to Deployment and Service.
- **k8s-service-deployment-pods-ingress**: Extends previous configurations by adding Ingress to enable external HTTP/HTTPS access.

Each folder contains a `README.md` file with detailed explanations for each Kubernetes object and commands to apply and manage them.

## Getting Started with Minikube

Minikube is a tool that lets you run Kubernetes locally. Follow these steps to set up Minikube and deploy the sample application.

### 1. Install Minikube

Follow the [Minikube installation guide](https://minikube.sigs.k8s.io/docs/start/) to install Minikube on your local machine.

### 2. Start Minikube

Run the following command to start a local Kubernetes cluster:

```sh
minikube start
```

This command sets up a Kubernetes environment on your local machine.

### 3. Deploy the Application

In each configuration folder, apply the Deployment and Service configurations to deploy your application.

#### Example Commands:

```sh
kubectl apply -f deployment.yaml
kubectl apply -f service.yaml
```

### 4. Check Deployment Status

Use the following commands to check the status of your deployments, pods, and services:

```sh
kubectl get deployments
kubectl get pods
kubectl get services
```

### 5. Access the Application

#### Access with Minikube

If you are using a **LoadBalancer** service type, Minikube provides an easy way to access your service:

```sh
minikube service <service-name>
```

Replace `<service-name>` with the name of your service (e.g., `sample-node-service`). This command will open the service in your default web browser or provide a URL for manual access.

#### Port Forwarding to Localhost (Optional)

If you want to access the service on localhost instead, use port forwarding:

```sh
kubectl port-forward service/<service-name> 3000:80
```

Now you can open `http://localhost:3000` in your browser to access the application.

## Step-by-Step Deployment Summary

### Step 1: Set Up Minikube
- Install Minikube and start the cluster.

### Step 2: Clone or Set Up the Sample Kubernetes Project
- Navigate to the specific configuration folder (`k8s-service-deployment`, `k8s-service-deployment-pods`, `k8s-service-deployment-pods-ingress`) as per your needs.

### Step 3: Deploy the Application
1. Apply Deployment and Service configurations:

   ```sh
   kubectl apply -f deployment.yaml
   kubectl apply -f service.yaml
   ```

2. Check the Deployment Status:

   ```sh
   kubectl get deployments
   kubectl get pods
   kubectl get services
   ```

### Step 4: Access the Application with Minikube

If using **LoadBalancer**, access it through Minikube’s `service` command:

```sh
minikube service sample-node-service
```

This opens the application in your browser or provides a URL to check your application.

**Expected Output**:

You should see a message like:

```
Hello from Kubernetes Node App!
```

This confirms that your application is running successfully on Kubernetes.

### Additional Options

#### Port Forwarding (Optional)
To test the service on `localhost`, use:

```sh
kubectl port-forward service/sample-node-service 3000:80
```

Then open `http://localhost:3000` in your browser.

---

Let us know if you encounter any issues or need further customization!

