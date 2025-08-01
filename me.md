```mermaid
graph TD
    A[User/Client] -->|HTTP/HTTPS| B(Application Load Balancer - ALB)
    B -->|Routes Traffic| C[ECS Service]
    C --> D[ECS Task (Container)]
    D -->|Runs on| E[EC2 Instance 1]
    D -->|Runs on| F[EC2 Instance 2]
    D -->|Runs on| G[EC2 Instance N]
    E & F & G -->|Scaling| H[Auto Scaling Group]
    H -->|Managed by| I[Amazon ECS Cluster]
    I --> J[VPC + Subnets]
    J --> K[Internet Gateway]
    L[Amazon ECR] -->|Stores/Pulls| D
    M[CloudWatch] -->|Logs/Metrics| C
```
