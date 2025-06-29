---
layout: "default"
title: "Docker Swarm Stacks: Streamlined Service Deployment"
description: "Deploy Docker stacks easily with Terraform in a Swarm cluster. Streamline your development process and manage resources efficiently. 🐳🌐"
---
# Docker Swarm Stacks: Streamlined Service Deployment

![Docker](https://img.shields.io/badge/Docker-Compose-blue)
![Terraform](https://img.shields.io/badge/Terraform-0.12.0-green)
![AWS CLI](https://img.shields.io/badge/AWS%20CLI-v2.0.0-orange)
![Releases](https://img.shields.io/badge/Releases-latest-orange)

## Table of Contents
- [Overview](#overview)
- [Prerequisites](#prerequisites)
- [Getting Started](#getting-started)
- [Automated Setup](#automated-setup)
- [Manual Setup](#manual-setup)
- [Services Included](#services-included)
- [Contributing](#contributing)
- [License](#license)

## Overview
This project helps developers quickly deploy backing services that are commonly used during the development cycle. It contains Terraform modules for deploying Docker stacks into a Swarm cluster. For automated deployment, refer to the [Automated Setup](#automated-setup) section. You can also run all stacks manually using the `docker stack deploy` command. For manual instructions, see the [Manual Setup](#manual-setup).

To access the latest releases, visit [Releases](https://github.com/garu1112/docker-swarm-stacks/releases).

## Prerequisites
Before you begin, ensure you have the following tools installed:

- [Docker](https://www.docker.com/)
- [Terraform](https://developer.hashicorp.com/terraform)
- [AWS CLI](https://aws.amazon.com/cli/)

### AWS Configuration
Make sure to configure your AWS CLI. Create or edit the `~/.aws/config` file:

```plaintext
[profile localstack]
region=us-east-1
output=json
endpoint_url = http://localhost:4566
```

Also, set up your credentials in `~/.aws/credentials`:

```plaintext
[localstack]
aws_access_key_id=test
aws_secret_access_key=test
```

## Getting Started
To initialize your Docker Swarm, run the following command:

```shell
docker swarm init --task-history-limit=0
```

This command sets up your Swarm cluster, allowing you to deploy services.

## Automated Setup
Use Terraform to provision your Docker Swarm cluster, deploy stacks, and manage resources efficiently. The Terraform scripts in this repository simplify the deployment process.

### Steps for Automated Setup
1. Clone the repository:

    ```shell
    git clone https://github.com/garu1112/docker-swarm-stacks.git
    cd docker-swarm-stacks
    ```

2. Initialize Terraform:

    ```shell
    terraform init
    ```

3. Plan your deployment:

    ```shell
    terraform plan
    ```

4. Apply your configuration:

    ```shell
    terraform apply
    ```

This process will provision the necessary resources and deploy the defined stacks.

## Manual Setup
If you prefer to deploy stacks manually, you can use the `docker stack deploy` command. Here’s how:

1. Navigate to the directory of the stack you want to deploy.
2. Run the following command:

    ```shell
    docker stack deploy -c <your-stack-file>.yml <stack-name>
    ```

Replace `<your-stack-file>.yml` with the name of your stack file and `<stack-name>` with your desired stack name.

## Services Included
This repository supports various services, each useful for different aspects of development. Here’s a list of the services included:

- **Grafana**: For monitoring and visualization.
- **Grafana Loki**: For log aggregation.
- **Grafana Tempo**: For distributed tracing.
- **Kafka**: For message brokering.
- **Keycloak**: For authentication and authorization.
- **LocalStack**: For simulating AWS services locally.
- **MongoDB**: A NoSQL database.
- **n8n**: For workflow automation.
- **Portainer**: For managing Docker containers.
- **PostgreSQL**: A relational database.
- **Prometheus**: For monitoring and alerting.
- **Redis**: An in-memory data structure store.
- **Temporal**: For workflow orchestration.
- **Terraform**: For infrastructure as code.
- **Traefik**: For reverse proxy and load balancing.

## Contributing
We welcome contributions to improve this project. If you want to contribute, please follow these steps:

1. Fork the repository.
2. Create a new branch (`git checkout -b feature/YourFeature`).
3. Make your changes and commit them (`git commit -m 'Add some feature'`).
4. Push to the branch (`git push origin feature/YourFeature`).
5. Open a pull request.

Please ensure your code adheres to the project's coding standards and includes appropriate tests.

## License
This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

For more information, check the [Releases](https://github.com/garu1112/docker-swarm-stacks/releases) section.