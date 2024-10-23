# Tech Challenge - SRE

Welcome to our SRE tech challenge. This challenge is designed to evaluate your skills in deploying, configuring, and documenting a robust application stack using Infrastructure as Code (IaC) principles. We would like you to showcase your SRE skills while providing comprehensive documentation by completing all 3 main tasks and at least one of the three optional tasks of the challenge below.

## Challenge

### Task 1: Deploy a Kubernetes Cluster
- Provision a Kubernetes cluster.
- Ensure the cluster is accessible and functioning properly.

### Task 2: Deploy ArgoCD
- Install ArgoCD in the `argo` namespace.
- Configure ArgoCD to connect to the Kubernetes cluster and track application deployments.

### Task 3: Deploy Keycloak
- Install Keycloak in the `identity` namespace using Helm and ArgoCD.
- Configure Keycloak for user authentication and authorization.
- Update ArgoCD configuration to authenticate with Keycloak.

## Optional Tasks

### Optional Task 1: Deploy Traefik as Ingress Controller
- Install Traefik as an ingress controller in the `ingress` namespace using Helm and ArgoCD.
- Configure Traefik to handle external traffic routing for the application stack.

### Optional Task 2: Deploy PostgreSQL
- Install PostgreSQL in the `database` namespace using Helm and ArgoCD.
- Configure PostgreSQL for secure and reliable data storage.

### Optional Task 3: Deploy Monitoring
- Install a monitoring solution, such as Prometheus and Grafana, to monitor the application stack's health and performance.
- Configure the monitoring solution to collect metrics from the deployed components.

## Documentation and Code Hosting
- Document the entire process, including installation steps, configurations, and explanations for the chosen solutions.
- Host all code (Terraform configurations, Helm charts) in a Git repository.

## Production Readiness
- Provide a concise summary of the steps involved in making the deployed application stack production-ready, including options you didn’t work on.
- Discuss considerations such as high availability, security, scalability, and disaster recovery.

## Success Criteria
- We are interested to see your skills towards successfully deploying and configuring the aforementioned application stack.
- Bonus points for well-structured documentation, clear explanations, and insightful comments.
- We are also interested in your ability to demonstrate a deep understanding of the technologies involved.

## My tasks
- Deploy Loki for log aggregation [maybe with Vector https://vector.dev/]
- Deploy cert-manager on and use Let's Encrypt to sign a TLS certificate for an HTTPS website 
[https://cert-manager.io/docs/tutorials/getting-started-aws-letsencrypt/] [https://akyriako.medium.com/ssl-tls-for-kubernetes-with-cert-manager-and-lets-encrypt-87846ca74cb4]
- Deploy a cache [Redis] in front of the db
- Add linkerd service mesh


## Steps
kubectl create ns argocd 
kubectl apply -n argocd -f ./argo/argocd-2.10.7.yaml
# Get the password
argocd admin initial-password -n argocd
# Install the secret
kubectl apply -f argo/repo-devops-setup.yaml
