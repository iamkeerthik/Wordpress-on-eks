# Wordpress-on-eks
Hosting simple wordpress site with mysql on eks cluster

Step-01: Create EKS Cluster using eksctl
It will take 15 to 20 minutes to create the Cluster Control Plane

```
# Create Cluster
eksctl create cluster --name=eksdemo1 \
                      --region=us-east-1 \
                      --zones=us-east-1a,us-east-1b \
                      --without-nodegroup 

# Get List of clusters
eksctl get cluster                  
```

Step-02: Create & Associate IAM OIDC Provider for our EKS Cluster

```
# Template
eksctl utils associate-iam-oidc-provider \
    --region region-code \
    --cluster <cluter-name> \
    --approve

# Replace with region & cluster name
eksctl utils associate-iam-oidc-provider \
    --region us-east-1 \
    --cluster eksdemo1 \
    --approve
    
  ```
