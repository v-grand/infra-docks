# infra-deployer

`infra-deployer` is a repository template for automated infrastructure deployment based on plug-in `infra-*` modules. It can be used as a CLI utility or as a REST/gRPC service embedded in CI/CD pipelines or lab environments.

## 📁 Project Structure

```
infra-deployer/
├── Dockerfile
├── Makefile
├── .env.example
├── deploy/
│   ├── __init__.py
│   ├── cli.py
│   ├── core.py
│   ├── terraform.py
│   ├── ansible.py
│   └── config.yaml
├── infra-modules/
│   ├── infra-core/ (git submodule)
│   ├── infra-network/
│   └── infra-monitoring/
├── scripts/
│   └── run_deploy.sh
├── tests/
│   └── test_core.py
├── .github/
│   └── workflows/
│       └── ci.yml
└── README.md
```

## ⚙️ Key Components

- **CLI Interface (`cli.py`)**: Provides `deploy`, `destroy`, `plan`, and `status` commands.
- **Terraform/Ansible Wrappers**: Manages module execution, logging, and dry-runs.
- **`infra-*` Submodules**: Pluggable infrastructure modules.
- **`Makefile`**: Commands for `run`, `test`, `lint`, and `build`.
- **CI/CD**: GitHub Actions for testing, linting, and building.

## 🧪 Testing

- `pytest` with `mock` for unit and integration tests.
- Aims for ≥ 80% test coverage.
- Validates CLI commands and core logic.

## 📚 Documentation

- `README.md` with setup instructions, project structure, and module integration guides.
- Supports configuration via `.env` and `config.yaml`.
- Can be extended to a REST API.

## 🧩 Integration

- Used as a CLI in `u-cloud24-platform`.
- Can be called from any CI/CD pipeline.
- Supports lab scenarios and automation.

## 🚀 Getting Started

To use `infra-deployer` as a template for a new service:

```bash
# Clone the template
cookiecutter gh:v-grand/infra-deployer-template

# Install dependencies
pip install -r requirements.txt

# Run the CLI
python -m deploy.cli deploy all
```

This template can be used as a basis for creating infrastructure management services, laboratories, CI/CD integrations, and internal platforms.
