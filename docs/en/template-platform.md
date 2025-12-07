# Microservice Platform Template

This repository serves as a template for creating a microservice-based platform. It includes everything needed for local development, testing, CI/CD, and deployment.

## Getting Started

### Prerequisites

- Docker
- Docker Compose
- Git

### Installation

1.  **Clone the repository:**

    ```bash
    git clone --recurse-submodules https://github.com/your-username/platform-template.git
    cd platform-template
    ```

2.  **Configure environment variables:**

    Copy `.env.example` to `.env` and modify the values if necessary.

    ```bash
    cp .env.example .env
    ```

3.  **Start the services:**

    ```bash
    make up
    ```

    This will start all services in the background.

## Testing

To run the tests, execute:

```bash
make test
```

## CI/CD

The CI pipeline is configured using GitHub Actions. It automatically runs on every push to the `main` branch or when a pull request is created.

## Deployment

Kubernetes manifests for deployment are located in the `k8s` directory.

## Submodules

This repository uses submodules to manage microservices. To update all submodules to the latest commits, use:

```bash
git submodule update --remote --merge
```
